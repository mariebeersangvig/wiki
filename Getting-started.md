# Getting started with
![<sesam logo](https://github.com/simenjorgensen/training/blob/master/sesamlogo.png)
***
# Table of contents 
#### [1 Introduction](https://github.com/sesam-community/wiki/wiki/Getting-started#1-Introduction-1)
#### [2 Glossary](https://github.com/sesam-community/wiki/wiki/Getting-started#2-Glossary-1)
#### [3 Prerequisite for Installation](https://github.com/sesam-community/wiki/wiki/Getting-started#3-Prerequisite-for-Installation-1)
#### [4 Setting up our Sesam node](https://github.com/sesam-community/wiki/wiki/Getting-started#4-Setting-up-our-Sesam-node-1)
- [4.1 Sign up](https://github.com/sesam-community/wiki/wiki/Getting-started#41-sign-up)
- [4.2 Import data](https://github.com/sesam-community/wiki/wiki/Getting-started#42-import-data)
#### [5 Creating our first pipe](https://github.com/sesam-community/wiki/wiki/Getting-started#5-creating-our-first-pipe-1)
- [5.1 Naming conventions](https://github.com/sesam-community/wiki/wiki/Getting-started#51-naming-conventions)
#### [6 Basic functions](https://github.com/sesam-community/wiki/wiki/Getting-started#6-basic-functions-1)
- [6.1 Transformation](https://github.com/sesam-community/wiki/wiki/Getting-started#61-transformation)
- [6.2 Check out the Lab](https://github.com/sesam-community/wiki/wiki/Getting-started#62-check-out-the-lab)
- [6.3 Merge](https://github.com/sesam-community/wiki/wiki/Getting-started#63-merge)
- [6.3.1 Merging sources](https://github.com/sesam-community/wiki/wiki/Getting-started#631-merging-sources)
- [6.3.1.1 Global datasets](https://github.com/sesam-community/wiki/wiki/Getting-started#6311-global-datasets)
- [6.3.1.2 Namespace identifiers](https://github.com/sesam-community/wiki/wiki/Getting-started#6312-Namespace-identifiers)
- [6.3.1.3 Labs 3](https://github.com/sesam-community/wiki/wiki/Getting-started#6313-labs-3)
- [6.3.2 Merging with DTL](https://github.com/sesam-community/wiki/wiki/Getting-started#632-merging-with-dtl)
- [6.4 Hops](https://github.com/sesam-community/wiki/wiki/Getting-started#64-hops)
- [6.4.1 Labs 4](https://github.com/sesam-community/wiki/wiki/Getting-started#641-labs-4)
- [6.5 Apply-hops](https://github.com/sesam-community/wiki/wiki/Getting-started#65-apply-hops)
- [6.5.1 Labs 5](https://github.com/sesam-community/wiki/wiki/Getting-started#6.51-labs-5)
- [6.5.2 Add or merge apply-hops?](https://github.com/sesam-community/wiki/wiki/Getting-started#652-should-i-add-or-merge-an-apply-hops)
- [6.6 Labs 6](https://github.com/sesam-community/wiki/wiki/Getting-started#66-labs-6)
#### [7 Sinks](https://github.com/sesam-community/wiki/wiki/Getting-started#sinks-1)
- [7.1 CSV endpoint sink](https://github.com/sesam-community/wiki/wiki/Getting-started#71-CSV-endpoint-sink)
- [7.2 Labs 7](https://github.com/sesam-community/wiki/wiki/Getting-started#72-labs-7)
- [7.3 SQL database to CSV file output step by step](https://github.com/sesam-community/wiki/wiki/Getting-started#73-SQL-database-to-CSV-file-output-step-by-step)
- [7.3.1 Using secrets](https://github.com/sesam-community/wiki/wiki/Getting-started#731-using-secrets)
- [7.3.2 Creating a table in the database](https://github.com/sesam-community/wiki/wiki/Getting-started#732-creating-a-table-in-the-database)
- [7.3.3 Creating our CSV sink](https://github.com/sesam-community/wiki/wiki/Getting-started#733-creating-our-csv-sink)
- [7.4 SQL sink example configuration](https://github.com/sesam-community/wiki/wiki/Getting-started#74-sql-sink-example-configuration)
- [7.5 HTTP-endpoint and retrieving data](https://github.com/sesam-community/wiki/wiki/Getting-started#75-http-endpoint-and-retrieving-data)
- [7.5.1 Exposing datasets with HTTP-endpoint](https://github.com/sesam-community/wiki/wiki/Getting-started#751-exposing-datasets-with-http-endpoint)
- [7.5.2 Fetching data](https://github.com/sesam-community/wiki/wiki/Getting-started#752-fetch-data)

#### [8. Microservices](https://github.com/sesam-community/wiki/wiki/Getting-started#8-microservices-1)
- [8.1 Workflow](https://github.com/sesam-community/wiki/wiki/Getting-started#81-workflow)
- [8.2 Getting started with microservices](https://github.com/sesam-community/wiki/wiki/Getting-started#82-getting-started-with-microservices)
- [8.2.1 Setting up](https://github.com/sesam-community/wiki/wiki/Getting-started#821-setting-up)
- [8.2.2 Testing](https://github.com/sesam-community/wiki/wiki/Getting-started#822-testing)
- [8.2.3 Push to Dockerhub](https://github.com/sesam-community/wiki/wiki/Getting-started#823-push-to-dockerhub)
- [8.2.4 Import to Sesam node](https://github.com/sesam-community/wiki/wiki/Getting-started#824-import-to-sesam-node)

***
# 1 Introduction
Welcome to this introduction to Sesam! This is a basic course that will guide you through what Sesam is, what it does and how it works.

Sesam is an Integration Platform that uses a unique Datahub approach for collection, connecting and sharing of data. The platform is optimized for collecting or receiving data from source systems, transforming data and pushing or providing data to target systems.

If you want to jump straight into Sesam and get hands-on, you can go right to [labs page](https://github.com/sesam-community/wiki/wiki/Labs) page and try them out. If you feel like you need some information before getting started you're on the right page. We'll link you to the labs as we go along learning Sesam.
***
# 2 Glossary
**Datasets:** Sesam stores its data as datasets that consist of entities. Datasets are used as sources for data transformation and stored as new datasets and sources for delivering data to target systems (endpoints).\
**Entity:** Sesam uses an entity data model as the core representation of data. Each entity is a dictionary of key-value pairs. Each key is a string and the value can be either a literal value, a list or another dictionary.\
**Pipe:** Defines the flow of data in Sesam. They consist of a source, and can also have a list of transformations and a sink. In addition every pipe has a pump that is scheduled to run at selected intervals and pull data entities from the source, through the transformations and put the results into the sink.\
**Pumps:** A scheduler that handles the mechanics of sending data from a source to a sink. It runs periodically or on a 'cron' schedule and reads entities from a data source and writes them to a data sink.\
**Sink:** Sinks are at the receiving end of pipes and are responsible for writing entities into an internal dataset or a target system.\
**Sources:** Sources consist of data entities and they come in many different formats. A source can provide data as datasets, SQL databases, CSV-files, RDF files such as XML, JSON data, REST APIs and others.\
**System**: A system component represents a computer system that can provide data entities. Its task is to provide common properties and services that can be used by several data sources, such as connection pooling, authentication settings, communication protocol settings and so on.\
**Transformation:** These are described using the Data Transformation Language (DTL). It is here you transform your data from many datasets to construct new entities into new datasets.

# 3 Prerequisite for Installation
  You must sign up using the Sesam Portal to install Sesam. The default installation type is a cloud based installation, but it's also possible to install Sesam on-premise or in a local cloud environment. This document assumes a cloud based installation. You can also access an existing Sesam installation by registering in the [Sesam Portal](https://portal.sesam.io/) and obtaining an invitation from someone with management permissions for the existing installation.

# 4 Setting up our Sesam node

## 4.1 Sign up

1. Go to https://portal.sesam.io/ and click on sign up.

2. Once you've signed up you'll see this page. Click on Request private trail.

<img src="https://github.com/simenjorgensen/training/blob/master/dashboard%20view.PNG" height="200" width="650"> 

3. Once you get the access from the Sesam team you'll get your own Dev Node card in the Dashboard. 

## 4.2 Import data

1. The first thing you need to do is to download the [training-config.json](https://github.com/sesam-community/wiki/blob/master/training-config.json?raw=true) and save it locally on your computer (left click url and "Save Link As..."). 

2. Go into you Dev Node. Click on **Datahub** in the left menu, and select the **Tools** tab.

<img src="https://github.com/simenjorgensen/training/blob/master/importdata.png" height="290" width="650"> 

3. Upload the file. Check the box **"Force upload (ignore validation errors)"**.

4. We have created some test data for you.  Go to **Variables** tab and paste the code below inside the curly brackets.
```json
  "node-env":"test"
```

5. Select **Pipes** in the menu on the left. Select the ```crm-person``` pipe and go to the **Config** tab. Preview the pipe by hitting **ctrl + Enter**. In the top right corner press **Start** then **Refresh**. It should look like the picture below. Notice that it says "Processed 10 last run" next to the **Start** button. You can also check the **Output** tab to see the entities.

![running pipe](https://github.com/simenjorgensen/training/blob/master/running_pipe.gif)

6. Repeat step 5 for ```azure-person```, ```firebase-person```, ```salesforce-userprofile``` and ```difi-postnummer``` pipes.
***

# 5 Creating our first pipe

1. Go into the new Sesam node.

2. Navigate to the **Pipes** view and click **New pipe**.

![New pipe](https://github.com/simenjorgensen/training/blob/master/new_pipe.gif)

![Pipe creation](https://github.com/simenjorgensen/training/blob/master/pipe%20config%20first%20pipe.PNG)

3. Select System **system:sesam-node** and Provider **crm-person**, then click **Replace** to add a pipe configuration from template.

4. Change the value of the ```"_id"``` property in the pipe config to ```crm-person-myfirstpipe``` in the pipe config.

5. Click **Add DTL transform** to add a transform property to your config.

6. Hit **ctrl + Enter** to preview the result of the config and observe that the ```"_id"``` of the entity seen in the **Source data** is the same as the one in in the **Result**.

7. Click **Save**.

We have now made our first pipe! Feel free to browse the different tabs of this pipe and explore. We can always find the pipe in the pipe list of our **Pipes** view.

If you click **Start** on the pipe it will run with the config you have created. After this you can find all the resulting entities in the **Output** tab of the pipe.

## 5.1 Naming conventions
To ensure we have a structured set of pipes that stay manageable in a bigger system we need to stick to a convention when naming them. Below is our recommended way of naming pipes.

**Input pipe:**  \<name-of-source>-\<name-of-object>  
**Internal pipe:**  global-\<name-of-object>  
**Internal pipe:**  \<purpose>-\<name-of-object>  
**Outgoing pipe:** \<name-of-object>-\<name-of-sink>  
**Output pipe:**  \<name-of-object>-\<name-of-sink>-endpoint 
***

# 6 Basic functions
## 6.1 Transformation

```json
"transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"],
        ["add", "Type", "customer"],
        ["add", "Fullname",
        	["concat","_S.FirstName"," ","_S.LastName"]],
        ["add","Firstname-lower",
        	["lower","_S.FirstName"]],
        ["add", "part-of-string",
        	["substring",0,4,"_S.FirstName"]],
        ["add", "fullname-lower-case",
                ["concat","_T.Firstname-lower"," ","_S.LastName"]],
        ["remove", "Username"]
      ]
    }
  }
```
Here we have the same system setup as before, but we have added some functions inside the transform. 
- The ```["copy","*"]``` copies everything from the dataset into the sink.
- The first ```["add"]``` creates a new property named ```"Type"``` that has the value ```"customer"```.
- The second ```["add"]``` creates a new property named ```"Firstname"``` which is constructed by using the function  concatenate (```["concat"]```).
- The third ```["add"]``` uses the function ```["lower"]``` to make all characters lower case.
- The fourth ```["add"]``` uses the function ```["substring"]``` to make a substring of the ```"FirstName"```.
- The fifth ```["add"]``` uses the function ```["concat"]``` to combine the lower cased first name with the last name.
- The ```["remove"]``` function removes the selected property. 

Notice the ```"_S.[property1]"``` and ```"_T.[property2]"```. The ```_S``` and ```_T``` are called variables and refer to the source and the target respectively. 
***
## 6.2 Check out the Lab
The [Labs page](https://github.com/sesam-community/wiki/wiki/Labs) hepls us get more hands on with Sesam. Head over there and do the first two labs to get more experience transforming data.
***
## 6.3 Merge

Merging gives us an aggregated representation of two or more datasets​​.

### 6.3.1 Merging sources

We can create an aggregated dataset source that contains all the data from multiple dataset through using source type ```"merge"```. With this merge type we will join datasets through properties that have corresponding values across different datasets. The resulting aggregated dataset will contain entities with all the properties from the different datasets.

![Database tables showing that only entities with some identical parameter value will combine into the same entity in our merged dataset](https://github.com/simenjorgensen/training/blob/master/db%20table%20after%20merge.PNG)
When merging datasets we need to combine entities through identical values across datasets. In the image above we merge datasets A and B through their "lastname" properties, and B and C through their "email" properties. As we can see, the resulting dataset will have "null" values in the fields that can not be populated through entities with matching values.

This way you can for example, combine a customer dataset with an another customer dataset through the ```"lastname"``` and work with a entity that contains more customer info.
```json
  "source": {
	"type": "merge",
	"datasets": ["customerA  a", "customerB b"],
	"equality": [
  	["eq", "a.lastname", "b.lastname"]
	],
	"identity": "first",
	"version": 2
  }
```
With the ```“equality”``` property of the source we set the joining condition for the merge. The join expression ```["eq", "a.lastname", "b.lastname"]``` will combine entities where the lastname from ```”customer A”``` matches the ```”lastname”```from ```"customer B”```. Our source dataset will after the merge contain entities with data from both the customers.

The ```“identity”``` property specifies the ID of the resulting entity. Set to ```“first”``` it will use a single ID value from one dataset. This ID will be copied from the first dataset that contains one, in the order that the datasets are listed in the ```“source”``` property. Set to ```“composite”``` it will instead make a custom id composed of all the different IDs in the datasets.

The ```”version”``` property refers to the version of the merge source. The default value is 1, but version 1 is deprecated. Set this to ```2```.

In the configuration above we have given the datasets aliases in the source config for easy referencing later in the source configuration. As we added the ```store-customer``` dataset as ```“store-customer c”``` we can then later reference the ID of that dataset simply as ```“c.id”```.

#### 6.3.1.1 Global datasets

Global datasets are key to getting the most out of using Sesam. We combine data from sources with logically linked information to provide one common place to then retrieve this data from when needed. This will reduce the total number of pipes needed compared to a system where you get data from the original sources each time.

#### 6.3.1.2 Namespace identifiers

A namespaced identifier consists of two parts; a namespace and an identifier. The namespace part can consist of any character, including colons. The identifier part can consist of any character except colons (:).

Example of an entity with namespaces:
```json
{
  "_id": "users:123",
  "user:username": "erica",
  "user:firstname": "Erica",
  "user:manager": "~:users:101"
}
```
Namespace identifiers are recommended way for referring datasets for matching properties during transformations. Suppose, if you have three different person datasets and you want to merge on some common properties, like e-mail or SSN, then we should use namespace identifiers. The code below will add a namespace identifier, based on common SSN properties between datasets "crm-person" and "firebase-person" during transformation inside DTL of "crm-person". Same way, we need to create a namespace identifier between "azure-person" and "firebase-person" datasets so that we can refer them during merging.
```json
        ["make-ni", "firebase-person", "SSN"],
```
This will produce the following output:
```
   "crm-person:SSN-ni": "~:firebase-person:23072451376",
```
Now, you have unique namespace identifiers based on SSN, which you can refer now.
``` json
{
  "_id": "global-person",
  "type": "pipe",
  "source": {
    "type": "merge",
    "datasets": ["crm-person cp", "azure-person ap", "firebase-person fp"],
    "equality": [
      ["eq", "cp.SSN-ni", "fp.$ids"],
      ["eq", "ap.SSN-ni", "fp.$ids"]
    ],
    "identity": "first",
    "version": 2
  }
```

In the above code we are connecting the foreign keys, ```"SSN-ni"``` of ```"azure-person"```  and ```"crm-person"``` with the primary key, ```"$ids"```, of ```"firebase-person"```. You do not need to add the third equality between ```"azure-person"```  and ```"crm-person"``` as it will happen automatically. 
 

#### 6.3.1.3 Labs 3
Go to the [Labs page](https://github.com/sesam-community/wiki/wiki/Labs#lab-3) and do Lab 3.
***
### 6.3.2 Merging with DTL

We can merge entities in the transform section (DTL) with the ```["merge"]``` function. This will combine its input properties (for example Age, CellNumber and salary) into the target dataset .
```
    ["merge",
            ["list", {
              "Age": 40
            }, {
              "CellNumber": 7854216,
              "Salary": 400000
           }]
    ]
```
We will later see the use of the ```["merge"]``` function in combination with functions that fetch entities from other datasets.
***

## 6.4 Hops
```["hops"]``` joins two datasets and returns the entities where the specified parameters match.
```json
"transform": {​
    "type": "dtl",​
    "rules": {​
      "default": [​
        ["copy", "*"],​
        ["add", "order-data"​
          ["hops", {​
            "datasets": ["global-orders glo"],​
            "where": [​
                ["eq", "_S.custno", "glo.custno"]​
            ]​
          }
        ]​
      ]​
     }
    }
```
In this transform we first copy everything from the source dataset into the target. To do a ```["hops"]``` you first add a new property to the target dataset. Then, inside that ```["add"]``` you call on the ```["hops"]``` function to fetch entities from the specified dataset, in this example (```"global-orders"```). 

### 6.4.1 Labs 4
Go to the [Labs page](https://github.com/sesam-community/wiki/wiki/Labs#lab-4) and do Lab 4.

## 6.5 Apply-hops

There is also the function ```["apply-hops"]``` which is a combined ```["apply"]``` and ```["hops"]``` function. This adds another "rule" in the DTL configuration in which we can specify how to implement the entities fetched with the hops. You can read more about the ```["apply"]``` function [here](https://docs.sesam.io/DTLReferenceGuide.html#nested-transformations).

```json
"transform": {
  "type": "dtl",
  "rules": {
    "default": [
      ["copy", "*"],
      ["merge",
        ["apply-hops", "order", {
          "datasets": ["orders o"],
          "where": ["eq", "_S._id", "o.cust_id"]
        }]
      ]
    ],
    "order": [
      ["add","ID","_S._id"]
    ]
  }
}
```
This will retrieve orders through the hops expression and then add them using the order transformation rule. The output is a dataset where the ID of all orders are added to the customers from the source dataset.

### 6.5.1 Labs 5
Go to the [Labs page](https://github.com/sesam-community/wiki/wiki/Labs#lab-5) and do Labs 5.
***

### 6.5.2 Should I "add" or "merge" an apply-hops?

As you can see in the examples below we want to add the "City" and "Municipality" from another dataset to the source. In the two examples we have the same source but the difference is in how we use the ```["apply-hops"]```.
In the first case we ```["add"]``` a new property called ```"difi-data"``` which you can see in the results creates a dictionary containing "City" and "Municipality" in ```"difi-data"```. 
```json
"transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"],
        ["add","difi-data",
          ["apply-hops", "foobar", {
            "datasets": ["difi-postnummer dip"],
            "where": [
              ["or",
                ["eq", "_S.azure-person:ZipCode", "dip.postnummer"],
                ["eq", "_S.crm-person:PostalCode", "dip.postnummer"]
              ]
            ]
          }]
        ],
        ["comment", "Below code will first check zipcode in azure-person dataset ,if it is null then it goes to crm-person dataset and so on. Basically we prioritize the order on most trusted values."],
        ["add", "zipcode",
          ["coalesce",
            ["list", "_S.azure-person:ZipCode", "_S.crm-person:PostalCode", "_S.firebase-person:ZipCode"]
          ]
        ]
      ],
      "foobar": [
        ["add", "Municipality", "_S.kommunenavn"],
        ["add", "City", "_S.poststed"]
      ]
    }
  }
```
Results:
![](https://github.com/simenjorgensen/training/blob/master/add_applyhops.png)
***
In the second example, instead of adding the ```["apply-hops"]```, we use ```["merge"]```. This will add the "City" and "Municipality" as properties in the target. 

```json
"transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy", "*"],
        ["merge",
          ["apply-hops", "foobar", {
            "datasets": ["difi-postnummer dip"],
            "where": [
              ["or",
                ["eq", "_S.azure-person:ZipCode", "dip.postnummer"],
                ["eq", "_S.crm-person:PostalCode", "dip.postnummer"]
              ]
            ]
          }]
        ],
        ["comment", "Below code will first check zipcode in azure-person dataset ,if it is null then it goes to crm-person dataset and so on.basically we prioritize the order on most trusted values."],
        ["add", "zipcode",
          ["coalesce",
            ["list", "_S.azure-person:ZipCode", "_S.crm-person:PostalCode", "_S.firebase-person:ZipCode"]
          ]
        ]
      ],
      "foobar": [
        ["add", "Municipality", "_S.kommunenavn"],
        ["add", "City", "_S.poststed"]
      ]
    }
  }
```
Results:
![](https://github.com/simenjorgensen/training/blob/master/merge_applyhops.png)

## 6.6 Labs 6
Go to the [Labs page](https://github.com/sesam-community/wiki/wiki/Labs#lab-6) and do Labs 6.
***
# 7 Sinks
Sinks are at the receiving end of pipes and are responsible for writing entities into a internal dataset or a target system.

Sinks can support batching by implementing specific methods and accumulating entities in a buffer before writing the batch. The size of each batch can be specified using the batch_size property on the pipe. See the section on batching for more information. We also recommend that you read about the [sinks](https://docs.sesam.io/configuration.html#sinks) in the documentation.

## 7.1 CSV endpoint sink
We will first look at setting up a sink to expose the output for a .csv (comma separated values) file. The CSV endpoint sink does not support pumping and the batching explained above. The only way to have entities flow through the pipe is by requesting the output as explained below.
```
"sink": {
  "type": "csv_endpoint",
  "columns": ["_id", "lastname", address"],
}
```
The sink config can include more parameters, but their default values are OK for our example and do not need to be listed and changed. For example ```"delimiter"```is set as ```","``` by default. Look up other parameters in the documentation if needed. The values listed in ```"columns"``` correspond to values in the output of the DTL.

After creating a pipe with a CSV endpoint sink you can go to the "Output" tab of the pipe. Here you can download the entity output. Select the number of entities you want to include and click "Download" to get a .csv file with the same name as the pipe. This can be viewed in a text editor to see the result, or you can open the file in e.g. Microsoft Excel. In Excel open a document, go to the "Data" tab and click "From Text/CSV".

You can also download the output by copying the cURL and creating your .csv file in a CLI like curl or Git Bash. Paste the cURL into you CLI and add " > my_file.csv" at the end. This will create the file at your current location. You can remove the entity limit and get all entities by removing "?limit=X" from the curl.

## 7.2 Labs 7
Go to the [Labs page](https://github.com/sesam-community/wiki/wiki/Labs#lab-7) and do Labs 7.
***
## 7.3 SQL database to CSV file output step by step 

In this next chapter we will walk you through the steps of using a SQL database as a source and create a CSV endpoint. First, if you don't have access to a SQL server you can sign up at [ElephantSQL](https://elephantsql.com) and select a free trial. 

Once you've set up you account click on **details** in the left menu. It should look like this:
<img src="https://github.com/simenjorgensen/training/blob/master/Elephant_SQL.png" height="400" width="600"> 

Now you are ready to create a new system. In [Sesam](https://portal.sesam.io/) go to **Systems** and select **New system**. In the **Choose template** select ```postgresql prototype``` (Because we're using ElephantSQL. Will be different for other sources). 

To fill inn the ```"database"```, ```"host"```, ```"password"``` and ```"username"``` go to your ElephantSQL and select details. From the figure above you'll see that you have the **Server**, **User & Default database** and **Password**. 

In the ```"_id"``` you'll create the name of the system (the same as creating a pipe). 
- ```"type"```: "system:postgresql" 
- ```"database"```: **User & Default database** 
- ```"host"```: **Server**
- ```"password"```: **Password**
- ```"username"```: **User & Default database**

### 7.3.1 Using secrets

<img src="https://github.com/simenjorgensen/training/blob/master/new_system3.png" height="400" width="600">

As you can see we are using secrets for the database, password and username. To do this go into the **Secrets** tab, click **Add secret**, give it a name (e.g. "password" for the password and "username" for the username) and paste the values from ElephantSQL. Read more about secrets [here](https://docs.sesam.io/security.html).

### 7.3.2 Creating a table in the database

Until now your database has been empty. If you are not familiar with SQL, do not worry. We have created some sample data for you. In ElephantSQL, click on **Browser** in the left menu. 

<img src="https://github.com/simenjorgensen/training/blob/master/elephantQuery.png" height="150" width="700">

1. Copy/paste:
```
CREATE TABLE EmployeeTable (
id SERIAL PRIMARY KEY,
firstname varchar(40),
lastname varchar(40),
DateOfBirth varchar(10),
Address varchar(40),
Salary int,
Department varchar(40)
);
```
Then click on **Execute**.

2. Copy/paste:
```
INSERT INTO EmployeeTable (id, firstname ,lastname ,DateOfBirth ,address,Salary,Department)
VALUES (1,'Larry','Johnson','27-05-1989','Country road 1',58000,'Sales'),
(2,'Mike', 'Jensen','05-27-1989','Upper street 3',62000, 'Marketing'),
(3,'Hannah', 'Jackson','10-12-1982','East road 5',60000,'Production'),
(4,'Phillip', 'Blackstone','08-02-1978','Sourt Street 23',49000,'Sales'),
(5,'Otto', 'Greene','03-20-1969','North street 65',48000,'HR'),
(6,'Siri', 'Stone','03-05-1989','Middle street 5',62000, 'Marketing'),
(7,'Olav', 'Olsen','11-30-1989','Down street 2',54000, 'Accounting');
```

Then click on **Execute**. We have now created a sample table with some properties with values. 

Head back to your Dev node. Now you can create a new pipe that pulls this table from the database. 

<img src="https://github.com/simenjorgensen/training/blob/master/new-pipe-db.png" height="400" width="500">

You are now free to transform the data as you want, but it is not needed and will be omitted here. 

### 7.3.3 Creating our CSV sink
 
<img src="https://github.com/simenjorgensen/training/blob/master/csv-endpoint.png" height="380" width="550">

There are multiple ways of viewing the data. The simplest is to download the file and opening it with Excel or any text editor. (If you are familiar with cURL you can copy the link and past it in terminal/command.)

<img src="https://github.com/simenjorgensen/training/blob/master/csv-sink.png" height="300" width="550">

Click **Download**. Open a new Excel document. Go to **Data** then select **From text**. Find the CSV-file and click **Get Data**.

Select as shown in figures below:

<img src="https://github.com/simenjorgensen/training/blob/master/csv-test.png" height="270" width="320"><img src="https://github.com/simenjorgensen/training/blob/master/csv-test2.png" height="270" width="320">

***
## 7.4 SQL sink example configuration

The outermost object would be your pipe configuration, which is omitted here for brevity:
```json
{
    "sink": {
        "type": "sql",
        "system": "my-mssql-system",
        "table": "customers"
    }
}
```


Each object is on the form:
```json
{
    "source_property": "name_of_property",
    "name": "name_of_column",
    "type": "string|integer|decimal|float|bytes|datetime|date|time|uuid|boolean",
    "max_size|max_value": 1234,
    "min_size|min_value": 1234,
    "precision": 10,
    "scale": 2,
    "allow_null": true|false,
    "primary_key": true|false,
    "index": true|false,
    "default": "default-value"
}
```

Let's look at an example:
```json
{
  "_id": "employeetable-endpoint",
  "type": "pipe",
  "source": {
    "type": "dataset",
    "dataset": "db-employee"
  },
  "sink": {
    "type": "sql",
    "system": "employee",
    "batch_size": 50,
    "bulk_operation_queue_size": 3,
    "bulk_operation_timeout": 600,
    "create_table_if_missing": true,
    "keep_failed_bulk_operation_files": false,
    "primary_key": ["id"],
    "schema": "dbo",
    "schema_definition": [{
      "type": "integer",
      "name": "id",
      "default": 1,
      "allow_null": false,
      "index": false,
      "max_value": 1000,
      "min_value": -1,
      "primary_key": true,
      "source_property": "id"
    }, {
      "type": "string",
      "name": "firstname",
      "default": "",
      "allow_null": true,
      "index": false,
      "max_size": 20,
      "min_size": 0,
      "primary_key": false,
      "source_property": "firstname"
    }, {
      "type": "string",
      "name": "lastname",
      "default": "",
      "allow_null": true,
      "index": false,
      "max_size": 50,
      "min_size": 0,
      "primary_key": false,
      "source_property": "lastname"
    }, {
      "type": "string",
      "name": "dateofbirth",
      "default": "",
      "allow_null": true,
      "index": false,
      "max_size": 50,
      "min_size": 0,
      "primary_key": false,
      "source_property": "dateofbirth"
    }, {
      "type": "string",
      "name": "department",
      "default": "",
      "allow_null": true,
      "index": false,
      "max_size": 50,
      "min_size": 0,
      "primary_key": false,
      "source_property": "department"
    }, {
      "type": "string",
      "name": "salary",
      "default": "",
      "allow_null": true,
      "index": false,
      "max_size": 50,
      "min_size": 0,
      "primary_key": false,
      "source_property": "sallary"
    }, {
      "type": "string",
      "name": "address",
      "default": "",
      "allow_null": true,
      "index": false,
      "max_size": 50,
      "min_size": 0,
      "primary_key": false,
      "source_property": "address"
    }],
    "table": "db-test-emlpoyee",
    "timestamp": "time_added",
    "truncate_table_on_first_run": false,
    "use_bulk_operations": false
  },
  "transform": {
    "type": "dtl",
    "rules": {
      "default": [
        ["copy",
          ["list", "id", "firstname", "lastname", "dateofbirth", "department", "sallary", "address"]
        ]
      ]
    }
  },
  "pump": {
    "mode": "manual"
  },
  "metadata": {
    "tags": ["test"]
  },
  "remove_namespaces": true
}
```
This sink configuration creates an SQL table containing data from the ```"db-employee"``` dataset.

***
## 7.5 HTTP-endpoint and retrieving data
We can expose the entities of a dataset in Sesam through an HTTP-endpoint and fetch them with an HTTP Get-request.


### 7.5.1 Exposing datasets with HTTP-endpoint
To expose a dataset from Sesam we create an HTTP-endpoint pipe in our Sesam node. Below is the configuration for a pipe called "person-crm-endpoint", which exposes the dataset 'person-crm'.

**Replace the dataset** in the ```"source"``` with the dataset you want data from and **name the pipe** accordingly in the ```"_id"```. We recommend setting the ```"_id"``` of the pipe as "name-of-dataset-endpoint".
```
{
  "_id": "person-crm-endpoint",
  "type": "pipe",
  "source": {
    "type": "dataset",
    "dataset": "person-crm"
  },
  "sink": {
    "type": "http_endpoint"
  }
}
```


### 7.5.2 Fetch data
To get hold of the data we have exposed in our HTTP-endpoint we send HTTP Get-requests from our client. Provided below are templates for implementing this in Python, Java or C# .Net.


####  Python
We will use Python's HTTP library Requests. This can be installed by running ```pip install requests``` in our Python interpreter.
```
import requests

url = "https://DATAHUB-URL.sesam.cloud/api/publishers/ENDPOINT-ID/entities"
JWT = "YOUR-JWT-TOKEN"

r = requests.get(url, headers={'Authorization': 'bearer '+JWT})
entities = r.text

print(entities)
```


#### Java
We will use Apache HttpClient to create a GET request and will need the following Maven dependency:
```
<dependency>
    <groupId>org.apache.httpcomponents</groupId>
    <artifactId>httpclient</artifactId>
    <version>4.5.4</version>
</dependency>
```
Java class:
```
package sesam;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import org.apache.http.HttpResponse;
import org.apache.http.client.methods.HttpGet;
import org.apache.http.impl.client.CloseableHttpClient;
import org.apache.http.impl.client.HttpClientBuilder;

public class ApacheHttpClientGet {

    public static void main(String[] args) throws IOException {

        String entities = getEntities();
        System.out.println(entities);
    }

    private static String getEntities() throws IOException {

        try (CloseableHttpClient client = HttpClientBuilder.create().build()) {

            String url = "https://DATAHUB-URL.sesam.cloud/api/publishers/ENDPOINT-ID/entities";
            String JWT = "YOUR-JWT-TOKEN";

            HttpGet request = new HttpGet(url);
            request.addHeader("Authorization", "Bearer "+JWT);
            HttpResponse response = client.execute(request);

            if (response.getStatusLine().getStatusCode() != 200) {
                // handle as preferred
                return null;
            }

            BufferedReader bufReader = new BufferedReader(new InputStreamReader(
                    response.getEntity().getContent()));

            return bufReader.readLine();
        }
    }
}
```


#### C# .Net
```
using System;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Threading.Tasks;

namespace Sesam
{
   class Program
   {
       static void Main(string[] args)
       {
           var entities = GetEntities().Result;
           Console.WriteLine($"Entities: {entities}");
           Console.ReadLine();
       }

       private static async Task<String> GetEntities()
       {
           var url = "https://DATAHUB-URL.sesam.cloud/";
           var apiUrl = $"/api/publishers/ENDPOINT-ID/entities";
           string jwt = "YOUR-JWT-TOKEN";

           using (var client = new HttpClient() { BaseAddress = new Uri(url) })
           {
               client.BaseAddress = new Uri(url);
               client.DefaultRequestHeaders.Accept.Add(new MediaTypeWithQualityHeaderValue("application/json"));
               client.DefaultRequestHeaders.Add("Authorization", $"Bearer {jwt}");

               using (var response = await client.GetAsync(apiUrl))
               {
                   if (response.StatusCode == System.Net.HttpStatusCode.OK)
                       return await response.Content.ReadAsStringAsync();

                   else return null;
               }
           }
       }
   }
}
```


#### Adaptation
To make these code implementations work with our HTTP endpoint we have to replace the capitalized parts of the URL and the JWT-token creation.

1. **Replace** ```DATAHUB-URL``` with the URL of our Sesam datahub. This URL is found just below the Sesam logo at the top-left corner of the page when logged into our node in the Sesam portal.

2. **Replace** the ```ENDPOINT-ID``` part of the URL with the ```"_id"``` of the endpoint pipe we want data from.

3. **Replace** ```YOUR-JWT-TOKEN``` with a JWT-token from our Sesam subscription. This is to provide authorization to access the HTTP-endpoint. The token is not retrievable through Sesam, but we might have already stored it somewhere for later use. We can find our JWT-token inside our .syncconfig-files if we have previously created these to support storing Sesam-configs locally. If we don't have access to our existing JWTs, we can create a new one in the Sesam portal under "Subscription" -> "JWT".

- Optionally we can add ```?limit=x``` or ```?since=x``` to the end of the URL in our get-call. _Limit_ has to be an integer and specifies the maximum number of entities to get. Adding _since_ will give you only the entities that have a higher value of "_updated" than the value you give _since_. The "_updated" property of the entities are either an integer or a timestamp, but _since_ is treated as a string. When using _since_ to only fetch entities that have been added since our previous request, we need to keep track the "_updated" value of the last entity fetched client side to have it available for the next call.

The complete URL could look like this: https://datahub-425aagcte.sesam.cloud/api/publishers/person-crm-httpendpoint/entities?since=255

All of these templates provide the data from the HTTP endpoint as a JSON-formatted string object named ```entities```. We can now replace the printing of this string with our own implementation to make use of the data.

***
# 8 Microservices

The DTL in Sesam is a powerful tool to transform our data. But sometimes we need to do something with our data that is outside the scope of the DTL. We can then create a microservice that does what we need and run it inside Sesam to serve those needs. We can also use a microservice when we need to connect to an external system where the connection point is not compatible with the Sesam source systems. The microservice can be made according to our preferrences and in any language.

<img src="https://github.com/simenjorgensen/training/blob/master/MS%20types.jpg" height="300" width="530"> 


As shown above, irrespective of nature or technologies of external system, we can easily connect with 
them using microservices to read, write and update data. Microservices add flexibility to do more with data than may be possible with DTL.


## 8.1 Workflow

Microservices in Sesam run in docker containers. These containers run on our Sesam-node in what we call a system. Below is a visual representation of the flow of hosting our microservice in Sesam.

<img src="https://github.com/simenjorgensen/training/blob/master/workflow%20ms.png" height="450" width="600"> 

We build a Docker image that is the blueprint for creating a container with our microservice. This image is not a container itself, but merely the recipe for creating the container. We can create and run as many containers as we want from the same image.

The Docker image is then pushed up to a repostory on Dockerhub. This repository can be private or made public. When hosted in the repository the image can be pulled by anyone with access.

Finally we pull the image from our Dockerhub repository and spin up a container on our Sesam-node. The container is created from the image and started. The Docker-commands for this are performed by Sesam. We simply specify the location of the image on Dockerhub in our Sesam system configuration and the contaner is spun up automatically.

***
## 8.2 Getting started with microservices 

### 8.2.1 Setting up 
 
First you need to sign up on [Docker](www.docker.com) and create a new repository.

<img src="https://github.com/simenjorgensen/training/blob/master/Docker__repo.png" height="400" width="650"> 

Then [download](https://www.docker.com/get-started) docker desktop. 

You now need to download Python. Here we're using Python 3.6 but you can use any version after 3.5.
Then install pip and flask. If you need help with this, follow the instructions [here](https://docs.sesam.io/overview.html#getting-started).

<img src="https://github.com/simenjorgensen/training/blob/master/flaskInstall.PNG" height="400" width="650"> 

Now you are ready to create the microservice.

Create a new project in Pycharm (or your preferred text editor). This tutorial will be using Pycharm. 
Name your project “Demo_MicroserviceProject”.

Inside your Demo_MicroserviceProject folder create a new text file called Dockerfile and paste:
```
FROM python:3-alpine

RUN apk update

RUN pip install --upgrade pip

COPY ./service/requirements.txt /service/requirements.txt
RUN pip install -r /service/requirements.txt
COPY ./service /service

EXPOSE 5000

CMD ["python3", "-u", "./service/DemoMicroservice.py"]
```
Then create a new folder called service inside your project root folder.

<img src="https://github.com/simenjorgensen/training/blob/master/MSproject.PNG" height="400" width="650"> 

Create a text file named "requirements.txt" inside the "service" folder and paste the following text inside it:

```Flask==1.0.2```

Then create a python file, also in the "service" folder, named "DemoMicroservice.py" with the following code:
```
from flask import Flask, jsonify

app = Flask(__name__)

orders = [
   {
       'id': 1,
       'Username': u'Unjudosely',
       'Orders': u'Thinkpad',
       'TotalSum': 8000
   },
   {
       'id': 2,
       'Username': u'Wimen1979',
       'Orders': u'MacbookPro',
       'TotalSum': 12000
   },
   {
       'id': 3,
       'Username': u'Gotin1984',
       'Orders': u'Chormebook',
       'TotalSum': 10000
   }
]


@app.route('/api/orders', methods=['GET'])
def get_orders():
    return jsonify({'orders': orders})


if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=5000)

```

<img src="https://github.com/simenjorgensen/training/blob/master/DemoService.PNG" height="400" width="650"> 

Create an image of the microservice in PyCharm's terminal window or any other CLI that you prefer:

```docker build -t <docker_username>/<your_repository_name>:<tagname> .```



To check that the you have created image run the command:

```docker images```


### 8.2.2 Testing 

To test that you can run a container from your image locally you can run it in command line/terminal. First we need to login to Docker. Run the command ```docker login``` and enter your Dockerhub **username** and **password** when prompted.

Next we'll need to run the image to create the container. 

```docker run -p <local_port>:<container_port> <docker_username>/<your_repository_name>:<tagname>```

Set ```<local_port>``` to 5000 and the ```<container_port>``` should be the same as the you expose in the Dockerfile. 

Then to check you can either go to the url in the browser or do:

```curl -v http://localhost:5000/api/orders``` in terminal

To stop the container running locally you can run:
```docker stop <container name or container id>```

### 8.2.3 Push to Dockerhub 

Then we need to push the image to the repository:

```docker push <docker_username>/<your_repository_name>:<tagname>```

Go to hub.docker.com and check that you can see the tagname in you repository.

<img src="https://github.com/simenjorgensen/training/blob/master/docker_push.png" height="400" width="650"> 

### 8.2.4 Import to Sesam node

Now we need to spin up the container in our Sesam node.

Create a new system in your node. Choose ```microservice prototype``` as template. Give it a proper name. 
Inside the ```"docker"``` parameter write: 

```json
"docker": {
    "image": "<docker_username>/<your_repository_name>:<tagname>",
    "port":5000
}
```

<img src="https://github.com/simenjorgensen/training/blob/master/systemconfigms.PNG" height="400" width="650"> 

Save it and click on **Status**. Click **Pull and restart**, then **Refresh** and **Check health**. You can also hit **Refresh** in the **log** so you see that it's running as it should. 

![](https://github.com/simenjorgensen/training/blob/master/system_microservice.gif)

Then create a new pipe.
Because our dataset does not have an ```"_id"``` property we need to add that. We could just use a normal ```["add"]``` function, but as you can see from the microservice, we’ve actually just created one property as a dictionary. We really want these as three entities. So we use this function: 

```json
["create",
	["apply", "create-entity", "_S.orders"]
```
This creates a new rule where we can add the ```"_id"```. Since the "id" in the microservice is an integer and Sesam only accepts string values for the ```"_id"``` we convert it with the ```["string"]``` function.

<img src="https://github.com/simenjorgensen/training/blob/master/pipe-orders-ms.PNG" height="400" width="650"> 

<img src="https://github.com/simenjorgensen/training/blob/master/pipe-orders-ms-output.PNG" height="400" width="650"> 
