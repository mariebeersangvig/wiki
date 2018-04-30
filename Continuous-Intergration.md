# This is a guide to setting up Sesam with a continous integration service

We will be using Travis CI as an example, but the principles should be applicable to most projects.

Prerequisites:

* One dedicated CI Node in Sesam cloud. This can be set up from portal.sesam.io 

* The subscription small will be enough for most use-cases. 

* A Github repository with your Sesam configuration, connected to Travis. Can be done from travis-ci.com/org depending on whether the project is open-source or closed-source,”.com” for closed-source, also called “Travis Pro”, isn’t free. 

[IMAGE?!]

Once you have a subscription you will have to create a new JWT and give it admin rights.

This is done under Subscription -> JWT and fill in the fields. We usually name this token by the name of the CI-service or something describing the purpose it has. 

In your original Sesam-config you will want to set up the pump to not run when the config is in test mode. This can be achieved by setting "mode" on the pump of outgoing pipes, like this:

`"pump": {
"mode": "$ENV(pump-mode)"}`

This can be set in addition to whatever was there before, a scheduled run for example. 