# Creating the Accounts Model
A good CRM application would have the capability to store and manage client account details. We will therefore start building a data placeholder where we can store information about our clients. Such a mechanism requires a database to store all the related information. In the world of AppFlower, databases are handled automatically through what we call ***Models***. 
So our first step is to create a new Model which we will name _Account_ to take care of this.

 The account Model will beside providing a way of storing client details also provide functionality to add new clients, update and delete existing clients.

# Creating the Account Model

Before creating the Account model, we should decide upon what details do we want to store about our clients. This will determine the structure of our Model. Well, in present case, we need the company name, address (city, zipcode, street address 1 & 2, State and country), contact details  (phone, fax, email and website) and an optional description field. Also we would like to referrer internally in our application to Accounts by using unique identifiers (IDs).

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/02_accontmodelcreated.png" rel="prettyPhoto" title=""><img alt="Account Model" src="/uploads/book/praticalcrm/thumb/02_accontmodelcreated.png" hspace="5" vspace="5"></a></div> 

***1. Create "Account" Model*** Okay. It's time to create our Account model in Studio. The Models Pane on the left should be already open. If it isn't, click it now. Click Add Model button at the bottom. Change the temporary name "NewModel" to account, then press enter.


The new model now gets generated and in a few seconds the Model Editor should show up. This tool has 2 tabs: ***one named like our model*** and a configuration tool, called ***Model Config***. For now we will be using the ***first tab***, which is almost like working with Spreadsheets.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/02_addfieldstoaccount.png" rel="prettyPhoto" title=""><img alt="Adding Fields to Account" src="/uploads/book/praticalcrm/thumb/02_addfieldstoaccount.png" hspace="5" vspace="5"></a></div> 

***2. Adding Fields*** To add our first field click on the table header for the spreadsheet named (id) and you will get another column available. We will keep the id field to uniquely identify the accounts. Let's now click on the header of the newly created column and rename it from "NewField" to _name_, this to store the account Company Name. Click Save to have the changes to take effect.

We have added 2 fields so far which is:
<pre>
id
name
</pre>

Seems like this is pretty straightforward, let's add the rest of the fields to the account model

<pre>
city
zipcode
address_line1
address_line2
state
country
phone
fax
email
website
description
</pre>

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/02_accounteditfielddropdown.png" rel="prettyPhoto" title=""><img alt="Adding Fields to Account" src="/uploads/book/praticalcrm/thumb/02_accounteditfielddropdown.png" hspace="5" vspace="5"></a></div> 

***3. Set field-type longvarchar*** Before (or after) saving the new Model structure we want to change a few field properties. We want to make the description field to contain long text. Since the default assigned field type is of varchar (this is like a small text upto 256 characters). Move your mouse course over the field you just named description, and you will see a drop-down icon. Click on the icon to expand the actions for the field and select Edit Field.


<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/02_accounteditfieldpopup.png" rel="prettyPhoto" title=""><img alt="Adding Fields to Account" src="/uploads/book/praticalcrm/thumb/02_accounteditfieldpopup.png" hspace="5" vspace="5"></a></div>

In the Edit Field window you will find the Field name which you already gave "description" and you will see just below type "varchar". Let's change the type of varchar to ***longvarchar***.

***4. Saving the Model*** Click Save to close this window, then hit the  Save button ***located at the top*** to have the new model applied to the database. That's it you now have created your first new model. Later on we will look into more advanced use-cases of models.

## Add content to our Account model
To make use of our Account model we could add some sample data. This will also help us when we are going to test our Application in the next chapter. So let's add the following content after adding the content remember to click ***Save*** so the content gets written to the Database.

<pre>
Name        | city       | zipcode   | country   | email              | website           | description
appflower   | copenhagen | 2100      | denmark   | info@appflower.com | www.appflower.com | the app builder company
</pre>