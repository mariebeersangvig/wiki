## Welcome to the lab!
These tasks will make you familiar with the basics of data transformation with Sesam. We recommend keeping the [documentation](https://docs.sesam.io/DTLReferenceGuide.html) at hand to look up syntax and concepts when needed.
​
***

## Lab 1
Scope: Transforming data.

* Create a new pipe​.
* Use the ```"crm-person"``` as source.
* Name it ```"[yourname]-crm-person"```.
* Create a new property called ```"FullName"``` by using the functions ```["add"]``` and ```["concat"]```.
* Run pipe and look at dataset.​
​

***
## Lab 2
Scope: Remove and add.

* Create a new pipe.
* Use the source that contains the property "Personalnummer".
* Copy all the properties.
* Remove the property "Personalnummer".
* By using the ```["add"]``` function, add a new property called "Birthday" by using the ```["substring"]```function.


***
## Lab 3

Scope: Merge multiple datasets in source to create a global.​

- Create New pipe. Call this pipe <your_name>-global-person.
- Select source system: system:sesam-node.
- Select provider type: merge prototype.​
- List these four datasets in the source, followed by an alias:  ```"crm-person crm"```, ```"firebase-person fir"```, ```"azure-person azu"``` and ```"salesforce-userprofile"```.
- Use ```["equality"]``` to merge the datasets on matching values.
- Set ```"identity"``` to ```"first"```.
- Set ```"version"``` to 2​.
- Add transform​.
- ```["copy" , "*"]```​.
***

## Lab 4

Scope: Hops

* In the same pipe that we created in lab 3 we want to 'hop' to another dataset with the ```["hops"]``` function. 
* Add a new property called difi-data. Inside the add use ```["hops"]``` to join on the ```"zipcode"```.
* Add the property "kommunenavn" from "difi-postnummer".
***

## Lab 5

Scope: Apply-hops

* In the same pipe that we created in lab 3 we want to 'hop' to another dataset with the ```["apply-hops"]``` function. 
* Add the property "poststed" from "difi-postnummer" by using ```["apply-hops"]```.
* Try to use ```["apply-hops"]``` inside an ```["add"]``` and a ```["merge"]```. See any difference?

***

## Lab 6

Scope: Enhancing the quality of data 

* Create new pipe, following naming conventions.
* Select the properties you want in output dataset (e.g. _id, FirstName, LastName, SSN, EmailAddress, ZipCode, City). 

***

## Lab 7

Scope : Publishing data to CSV-endpoint

* Create new pipe. Source from lab 6. Add transform and sink.​
* Look [here](https://github.com/sesam-community/wiki/wiki/Getting-started#71-csv-endpoint-sink) for help

***
​
***
## More labs

1. Create a pipe that uses "crm-person" and "firebase-person" as source. Use the ```["if"]``` function to check if the "FirstName" and the "GivenName" are equal. If so, remove "GivenName". 

2. Create a pipe that use "firebase-person" as source. In the transform do an ```["apply-hops"]``` with the "crm-person". In the new rule create a new property called "Birthyear" from the "Personalnummer" by adding "19" to the year in the "Personalnummer" (i.e. using ```["substring"]```). Then add a property "age-group" and use the function ```["case"]``` to group the entities by "Birthyear" (Check solutions for help).

3. Use the dataset you created in exercise 2 as source. Add "FirstName", "LastName", "Gender", "Address", "ZipCode", "Email", "Birthday", "age-group". Filter so that you only get the people in the age-group "61-80 years old".

4. Merge two datasets as source in pipe. In this exercise we don't want properties that have the same value to be shown in the output. Use ```["coalesce"]``` to do this.
***
​
