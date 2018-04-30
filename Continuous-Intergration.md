# This is a guide to setting up Sesam with a continous integration service

We will be using Travis CI as an example, but the principles should be applicable to most projects.

Prerequisites:

* One dedicated CI-node in Sesam cloud. This can be set up from portal.sesam.io 

* The subscription small will be enough for most use-cases. 

* A Github repository with your Sesam configuration, connected to Travis. Can be done from travis-ci.com/org depending on whether the project is open-source or closed-source,”.com” for closed-source, also called “Travis Pro”, isn’t free. 

[IMAGE?!]

Once you have a subscription you will have to create a new JWT and give it admin rights.

This is done under Subscription -> JWT and fill in the fields. We usually name this token by the name of the CI-service or something describing the purpose it has. 

In your original Sesam-config you will want to set up the pump to not run when the config is in test mode. This can be achieved by setting "mode" on the pump of outgoing pipes, like this:

`{`
	`"pump": {`
	`"mode": "$ENV(pump-mode)",`
	`"schedule_interval": 30`
	`}`
`}`

This can be set in addition to whatever was there before, a scheduled run for example. 

With this setup you will have to set the environment variable "pump-mode" to "manual" on your CI-node and the appropriate equivalent in your production environment, check [Sesam Docs](https://docs.sesam.io/configuration.html#pumps) for possibilities.

NOTE! the test-env.json is not downloaded with "sesam download" so it must be created locally.

[IMAGE]

The next step is to connect your Github-repository to the service you are using, log in with github credentials and connect your repository. 

You will also have to add the JWT you created earlier to allow access to the CI-service you are using. Typically it will be set as an environment variable. The name should be "JWT" and the value is the generated value from Sesam.

The target node should also be specified with the name "NODE" and the value you find in the portal under Subscription -> Network and as Default URL. Remove the "https://" and the "/api" and you have your value.

The option “Limit concurrent jobs” can be set to 1 if there are more than one project running on the same account. This may or may not be applicable depending on the service you choose to use.

To give the CI-service instructions on how to run sesam you need to create a file on your Github repository. In this example with Travis it will be called .travis.yml and contain two lines; 

"”install: bash <(curl -s https://raw.githubusercontent.com/sesam-io/sesam/master/install-latest.sh) 

script: cd node/ && ../sesam -version && ../sesam -vv test”" 

The first line tells the service where to get the sesam-client [Sesam CLI](https://github.com/sesam-io/sesam), and to install the latest version, the second line runs sesam-client from the default install folder with the option -vv (which is very verbose), root, so you should point this to the correct location. If you stand in node like we do in the example above, typically you have to move one level up to reach root. This can vary depending on how it looks in your repository. 

Locally, in your ./node folder you will have to create a new folder called “expected” where the expected output from the test will be placed. 

If you open your terminal of choice in the ./node folder and type the command “sesam update” will populate the expected-folder with data from the node. If it doesn't then you might have to add the sesam-client to you PATH. 

Run the command "sesam update" to generate expected data from the node if you have made any changes to the expected config. 

The test configuration is set in the PIPENAME.test.json-file that is created in the expected-folder.

[IMAGE]


If there is a known error with, for example, timestamps generated from Sesam you can choose to "blacklist" that field in the test to not crash it. This is done because the timestamp will never match if it's changed every time the pipe runs. The expected result has to match the actual result 100%. 

Empty arrays can also be stored as "<nil>", which is not the same as an empty array and when compared returns an error. To avoid this, "ignore":true is usually set in the .test.json-file. 

Another error that can occur is when you have a non-deterministic merge, which can be caused by running the pipes in a different order that expected, see where hops are applied. This may cause copying of entities and a result-set that is bigger than expected. 

This is the syntax for it, and some options: 

`{ `

`"blacklist": ["fieldname"], `

`"ignore": true/false (false doesn't do anything) `

`} `

for the full list, see: https://github.com/sesam-io/sesam under the header "Configuring tests" 

With this set up, your CI-service will now wait for pull request to github and then automatically test them. 

The thought behind continuous integration is that by merging you branches in to master more often, there is less to fix if something breaks. To read more about this go to wikipedia 