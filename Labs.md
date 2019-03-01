## Welcome to the lab!

These tasks will make you familiar with the basics of data transformation with Sesam. We recommend keeping the [documentation](https://docs.sesam.io/DTLReferenceGuide.html) at hand to look up syntax and concepts when needed.

To do these labs you will need to have a Sesam node set up with the [Training Node - config.json](https://github.com/simenjorgensen/training/blob/master/Training%20Node%20-%20config.json?raw=true) configuration. If you have set up your node following the [Getting started with Sesam](https://github.com/sesam-community/wiki/wiki/Getting-started#42-import-data) guide you are ready to do these labs. We recommend having a go at this by yourself, but there are clues provided on where to look for guidance if needed.

Good luck and have fun! 
***

## Lab 1
Scope: Transforming data.

* Create a new pipe​.
* Use the ```"crm-person"``` as source.
* Name it ```"[yourname]-crm-person"```.
* Create a new property called ```"FullName"``` by using the functions ```["add"]``` and ```["concat"]```.
* Run pipe and look at dataset.​
​

_If you need a hint on how to do this, look for the ```["concat"]``` function in the "global-person" pipe._
***
## Lab 2
Scope: Remove and add.

* Create a new pipe.
* Use a "person" source that contains the property "SSN".
* Copy all the properties.
* Remove the property "SSN".
* By using the ```["add"]``` function, add a new property called "Birthday" by using the ```["substring"]```function.


_Hint: Look up "remove" and "substring" in the documentation._
***
## Lab 3

Scope: Merge multiple datasets in source to create a global.​

- Create New pipe. Call this pipe <your_name>-global-person.
- Select source system: system:sesam-node.
- Select provider type: merge prototype.​
- List these four datasets in the source, with aliases:  ```"crm-person cp"```, ```"firebase-person fp"```, ```"azure-person ap"``` and ```"salesforce-userprofile sup"```.
- Use ```["equality"]``` to merge the datasets on matching values.
- Set ```"identity"``` to ```"first"```.
- Set ```"version"``` to 2​.
- Add transform​.
- ```["copy" , "*"]```​.


_Hint: Look at the source section of the "global-person" pipe._

***
## Lab 4

Scope: Hops

* In the same pipe that we created in lab 3 we want to 'hop' to another dataset with the ```["hops"]``` function. 
* Add a new property called difi-data. Inside the add, use ```["hops"]``` to join on the ```"zipcode"``` from azure-person OR ```"PostalCode"``` from crm-person with ```"postnummer"``` of "difi-postnummer".

_Hint: Look up hops in the Getting started guide and the documentation. You will also find the "or" function in the documentation._
***
## Lab 5

Scope: Apply-hops

* In the same pipe that we created in lab 3 we want to 'hop' to another dataset with the ```["apply-hops"]``` function. 
* Add a global property "City" and "Municipality" from "difi-postnummer" by using ```["apply-hops"]```.
* Try to use ```["apply-hops"]``` inside an ```["add"]``` and a ```["merge"]```. See any difference?


_Hint: Look at the transform section of the "global-person" pipe._
***
## Lab 6

Scope: Creating global properties

* In the global pipe we now want to create global properties for firstname, lastname, fullname, address, SSN, zipcode and customerid.
* Use ```["coalesce"]``` and ```["list"]``` functions to prioritize which source you want to pick from first. 


_Hint: Look at the transform section of the "global-person" pipe._
***
## Lab 7

Scope: Enhancing the quality of data 

* Create new pipe, following naming conventions.
* Copy these properties to the output dataset: CustomerId, firstname, lastname, FullName, Address, SSN, zipcode, City and Municipality. 


_Hint: Look at the transform section of the "person-crm" pipe._
***
## Lab 8

Scope : Publishing data to CSV-endpoint

* Create new pipe. Source from lab 6. Add transform and sink.​
* Look [here](https://github.com/sesam-community/wiki/wiki/Getting-started#71-csv-endpoint-sink) for help


_Hint: Look at the "person-crm-endpoint" pipe._
***
## More labs

A. Create a pipe that uses "crm-person" and "firebase-person" as source. Use the ```["if"]``` function to check if the "FirstName" and the "GivenName" are equal. If so, remove "GivenName". 

B. Create a pipe that use "firebase-person" as source. In the transform do an ```["apply-hops"]``` with the "crm-person". In the new rule create a new property called "Birthyear" from the "Personalnummer" by adding "19" to the year in the "Personalnummer" (i.e. using ```["substring"]```). Then add a property "age-group" and use the function ```["case"]``` to group the entities by "Birthyear".

C. Use the dataset you created in lab B as source. Add "FirstName", "LastName", "Gender", "Address", "ZipCode", "Email", "Birthday", "age-group". Filter so that you only get the people from one of the age-groups.

D. Merge two datasets as source in pipe. In this exercise we don't want properties that have the same value to be shown in the output. Use ```["coalesce"]``` to do this.
***
​
