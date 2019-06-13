# Getting started with Sesam's GDPR Platform

# Table of contents
#### [1 Introduction](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#1-introduction-1)
#### [2 Portal Setup](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#2-portal-setup-1)
- [2.1 Setting up](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#21-setting-up)
- [2.2 Establishing what we have and why](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#22-establishing-what-we-have-and-why)
- [2.2.1 Purposes](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#221-purposes)
- [2.2.2 Data types](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#222-data-types)
- [2.2.3 Excel sheet alternative for data types and purposes](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#223-excel-sheet-alternative-for-data-types-and-purposes)
- [2.4 Customize your portal](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#24-customize-your-portal)
#### [3 Data access request](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#3-data-access-request-1)
- [3.1 Request data](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#31-request-data)
- [3.2 Request handling by system owner](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#32-request-handling-by-system-owner)
- [3.3 Data subject can view data and execute their rights](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#33-data-subject-can-view-data-and-execute-their-rights)
#### [4 Automation of data request handling](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#4-automation-of-data-request-handling-1)
- [4.1 Import data](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#41-import-data)
- [4.2 Link data to data subject](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#42-link-data-to-data-subjects)
- [4.3 Update pre-built pipe](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#43-update-pre-built-pipe)
- [4.4 Working with "Related" data type levels](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#44-working-with-related-data-type-levels)
#### [5 Deletion or change requests](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#5-deletion-or-change-requests-1)
#### [6 GDPR unstructured data handling](https://github.com/sesam-community/wiki/wiki/GDPR-Platform#6-gdpr-unstructured-data-handling-1)

# 1. Introduction
With Sesams GDPR Platform you can handle your company's GDPR responsibilities. This guide will show you how to set up processing of incoming data requests from the company's data subjects.

# 2. Portal setup

## 2.1 Setting up

1. Go to [https://portal.sesam.io](https://portal.sesam.io) and click on sign up.

2. Once you have signed up click on **New GDPR portal**.

3. Fill in your contact and payment information.

4. You will then see your GDPR portal on the dashboard. From here you can add members to your site and administrate your subscription as shown in the picture below. 
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/DashBoard2.PNG" width="650" height="370">



5. When inside settings, set **name** of your GDPR portal and add a **description** that will be seen by the data subject. 
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/name_descr_gdpr.png" width="650" height="370">



6. Select **GDPR** in the left column navigator and fill in your domain name.
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/yourcompanydomain.png" width="650" height="370">

The domain name is the internet address (DNS name) where your GDPR data access portal should be available to the users (data subjects in GDPR lingo). You can choose any name you want, as long as it's not already in use by someone else. Your GDPR data access portal will then be available on the web (e.g. https://your-selected-name.sesamdata.com).

## 2.2 Establishing what we have and why
You need to identify what are your systems, which types of personal data are in those systems and what purposes gives you the right to have the personal data. 

### 2.2.1 Purposes
Navigate to the Purposes tab and create populate it with your purposes for having the data in your systems. The creation webform provides explanations for what each field represents. Below is an image of the purpose creation template. Make sure to fill in all fields marked with a star (*).
![purpose creation webform](https://github.com/sesam-community/wiki/blob/master/gdpr%20img/purpose%20creation.png?raw=true)

When a data access request has been processed the purpose is displayed to the data subject like in the following image:
![purpose as displayed to the data subject](https://github.com/sesam-community/wiki/blob/master/gdpr%20img/purpose%20displayed.png?raw=true)

### 2.2.2 Data types
Next, go to Data Types and fill in the data you have in your systems. Make sure to fill in all fields marked with a star (*). In the "Purposes" field you select the purposes you have created that apply to the data in question. The email-address(es) supplied in "Contact" will receive an email when somebody makes a request for this data.
![data type creation webform](https://github.com/sesam-community/wiki/blob/master/gdpr%20img/data%20type%20creation.png?raw=true)

The data related to the data subject can then be displayed like this when a data access request is served:
![data type as shown to the data subject](https://github.com/sesam-community/wiki/blob/master/gdpr%20img/data%20type%20displayed.png?raw=true)

### 2.2.3 Excel-sheet alternative for data types and purposes

Alternatively you can choose to upload the purposes and data types from an Excel-sheet. The sheet will have to contain the same info as you would input through the Sesam portal user interface.

#### Filling out the Excel template
1. Go to [this URL](https://docs.sesam.io/gdpr-data-types-purposes-configuration.html) and download the Excel file in the "GDPR Excel setup template file" link. 

![GDPR excel](https://github.com/simenjorgensen/training/blob/master/GDPR_download_excel.gif)

2. Fill in the **GDPR setup data** Excel template. There are examples in it for you to follow. Please note that there are three sheets in the file. Remember to fill in the contact information for the person responsible for the data in each system.
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/excel-GDPR%20setup%20data.PNG" width="650" height="370">

#### Uploading Excel-file to portal

1. Navigate to **GDPR** in the left column and then to **Setup**. 

2. **Upload** the GDPR setup data Excel file in the **Upload data type template** section after you have filled in the necessary information. 
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/excel-upload.PNG" width="650" height="370">

## 2.4 Customize your portal

You can customize you portal by **uploading your own logo** if you want to. 
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/yourcompany.png" width="650" height="370">

That's it! Your GDPR portal is all set.
***
# 3. Data access request

## 3.1 Request data

1. **The data subject can now log in** to your portal to request their data. The URL will be the one you chose in the setup process, for example yourcompany.sesamdata.com

![](https://github.com/simenjorgensen/training/blob/master/GDPR/login-GDPR.PNG)

2. The data subject can log in with their email or phone number. This is a two-factor secure login that requires the subject to confirm a one-time password. **Test logging in yourself!**

3. The data subject can now request their data or ask to be deleted
![](https://github.com/simenjorgensen/training/blob/master/GDPR/Request-for-GDPR_Data.PNG)

## 3.2 Request handling by system owner

1. The **system owners** specified in the GDPR Excel setup will receive an email about the request made by the data subject.
***
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/EmailRequest-for-GDPR_Data.PNG" width="500" height="150">

***
2. **Download** Request template for handling the access request

<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/GDPR-AccessRequest.PNG" width="600" height="350">

3. **Fill in** the Request template for the specific data subject. You can use field names that you find fitting and add as many columns as needed. Then **save** the Excel document.

<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/access-request-gdpr.png" width="670" height="350">

4. **Upload** the filled-in Request template in the portal. The access request is now handled.

5. The data subject will now be informed via email or text message that the data is available.
***
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/Email_GDPR_result_available_2.PNG" width="600">

***
## 3.3 Data subject can view data and execute their rights
When the data subject logs back in he or she can now **view their data** and **execute all their rights**.

<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/data_exposed.png" width="600" height="420">

- Right of access (art. 15)

- Consent (art. 7)

- Right to be forgotten (art. 17)

- Right to rectification (art. 16)

- Right to data portability (art. 20)

- Breach notification (art. 34)

- Right to object (art. 21)

- Right to not be subject to automated decision-making (art. 22)

- Right to restriction of processing (art. 18)

# 4. Automation of data request handling

If we have an automatic version of the GDPR platform we can set it up so that it handles data access requests automatically. The data will be delivered to the data subject without human intervention. We can do this because we use the Sesam integration platform with our GDPR platform. Using the Sesam integration platform means we make a copy of all the data we want to make available for the GDPR platform into its Sesam datahub. Once the data is available in the datahub, the system can serve data access requests on it's own.

To set up this automation we need to take care of a few things:
- **Import data** from our data systems to the datahub of the GDPR platform
- **Refer to the datasets** in the datahub in our data type definitions
- **Update** a pre-built pipe

## 4.1 Import data

We have to copy all the data from our source systems that contain data that could be served to our data subjects. We can import this data from different types of sources like databases, APIs, CSV- or XML-files. We do this by creating "input pipes" that copy all the data from a source. The pipes connect to external sources through "systems" in Sesam, which serve connection strings, connection pooling, authentication etc. Take a look at our [Getting started with Sesam](https://github.com/sesam-community/wiki/wiki/Getting-started) guide to learn how to configure pipes and systems to connect to external data sources.

For testing purposes we have pre-made a few pipe configurations with embedded test data. We can use these pipes to setup and test the automation with dummy data before connecting to our real data sources.

Create four new pipes and paste the configurations provided in the links below. We can change the values of the first entity of the embedded data in these configs to match our own email address. That way we can test the platform as a data subject ourselves.

- [salesforce-contact.json](https://github.com/simenjorgensen/training/blob/master/GDPR/salesforce-contact.json?raw=true)
- [salesforce-eventrelation.json](https://github.com/simenjorgensen/training/blob/master/GDPR/salesforce-eventrelation.json?raw=true)
- [salesforce-lead.json](https://github.com/simenjorgensen/training/blob/master/GDPR/salesforce-lead.json?raw=true)
- [salesforce-task.json](https://github.com/simenjorgensen/training/blob/master/GDPR/salesforce-task.json?raw=true)


## 4.2 Link data to data subjects
In our data type definitions we now also have to specify from which dataset the data is pulled. To do this we need to create and populate two extra fields in our data type definitions: "TypeID" and "Identifiers" . We can do this as we create the data types or we can edit them at a later time.

The "**TypeID**" field needs to have a value matching the **rdf:type** of the data, while the "**Identifiers**" field needs to contain the **namespace and identifier** of the attribute of the data we refer to in the data type definitions. See the image below for reference:

![lnk to data in data type definition](https://github.com/sesam-community/wiki/blob/master/gdpr%20img/data%20type%20for%20automation.png)

These identifiers are what connects the data in the datasets to the data subject that is requesting their data. As you can see we have chosen **EmailAddress** in this example, but other attributes may be as-well or better suited for identifying data subjects. It could also be multiple identifiers separated by comma (no spaces).

### Excel file data type definition alternative
If we wish to use an Excel file instead of the portal user interface to upload data types we then have to use [this Excel template](https://docs.sesam.io/_downloads/GDPR%20setup%20data%20automated.xlsx). In this template we need to populate the same two fields as described above.

## 4.3 Update pre-built pipe
1. Open pre-built pipe **custom-subject-data** and update this pipe with all our input datasets. Here we add four datasets **salesforce-contact**, **salesforce-eventrelation**, **salesforce-lead** and **salesforce-task** as our sources. After updating the pipe it should look like this:

```{
  "_id": "custom-subject-data",
  "type": "pipe",
  "source": {
    "type": "merge",
    "datasets": ["salesforce-contact sc", "salesforce-eventrelation se", "salesforce-lead sl", "salesforce-task st"],
    "equality": [],
    "identity": "first",
    "strategy": "compact",
    "version": 2
  }
```

2. Now we can check the output of another pre-built pipe **gdpr-subject-data-update** (remove the "user" filter to see the complete list of pipes). Check the output of this pipe and you should see all the entities from all four datasets. These entities will eventually go into data subject as per his or her data access request.

3. That's it! We can now make a request as a data subject using our GDPR portal for the related data stored with the company.


## 4.4 Working with "Related" data type levels:
1. Until now we are able to fetch data based on "Personal" data type level for corresponding identifier.
Now we will see how related data also gets fetched using "Related" data type level.
To test this functionality, we have now added a new row for "Related" data type level in our excel sheet as showing below.
<img src="https://github.com/simenjorgensen/training/blob/master/GDPR/gdpr-excel-related.png" width="720" height="210">

2. Save this excel file and upload to Sesam GDPR node.

3. Create the new pipe for "Related" level called **salesforce-attendee** in GDPR node.
- [salesforce-attendee.json](https://github.com/simenjorgensen/training/blob/master/GDPR/salesforce-attendee.json?raw=true)

4. Add this dataset entry info to pre-built pipe **custom-subject-data**.
```json
{
  "_id": "custom-subject-data",
  "type": "pipe",
  "source": {
    "type": "merge",
    "datasets": ["salesforce-contact sc", "salesforce-eventrelation se", "salesforce-lead sl", "salesforce-task st", "salesforce-attendee sa"],
    "equality": [],
    "identity": "first",
    "strategy": "compact",
    "version": 2
  }
}
```
4. That's it. You can now make the request and will be able to see all the personal data as well as related data. Make sure you run all the pipes after resetting it to get latest change. 

# 5. Deletion or change requests

The data subject has the right to be forgotten (deleted) or have their data rectified (changed). To support rectification of data you will have to set up the GDPR data access portal to allow for it. You can read about how to do that in the [databrowser guide](https://docs.sesam.io/databrowser-guide.html).

When a deletion or change request is submitted to a manually updated GDPR platform, an email will be sent to the address(es) listed as "Contact" in our uploaded "Purposes and Data types" excel sheet for the relevant data type(s). This recipient of this email needs to be a user in the Sesam portal assigned the "GDPR operations" role. The recipient of the request will then have to manually update the source systems as per the request. Then the GDPR operator will have to reupload a an excel sheet as if a new data access request has been submitted to reflect the changes.

For an automated GDPR platform it is possible to process change and deletion requests automatically by triggering changes or deletions directly in the source systems. See the [GDPR platform developer documentation](https://docs.sesam.io/gdpr-platform-developer-docs.html#gdpr-platform-developer-docs) for information about automation and the APIs offered for implementing such a mechanism.

# 6. GDPR unstructured data handling

Up to this point we have been working with "structured" data. However, data is not always going to be structured in the real world. Fortunately, Sesam GDPR node also supports handling of GDPR unstructured data. Visit [GDPR unstructured data support](https://docs.sesam.io/gdpr-platform-developer-docs.html#gdpr-unstructured-data) to learn more about this.