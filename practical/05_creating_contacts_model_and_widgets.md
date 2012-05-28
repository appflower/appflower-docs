# Creating Contacts Model and Widgets

In this chapter we'll build the next important part of our CRM application: an address book to store our contacts. The component will allow you to manage the details of the contacts affiliated with your accounts. Just like the account manager, this will also consist of a Model and a List and an Edit widget, as these can provide all the tools you need.

We'll begin with creating the contacts model to have a nice database background, then we'll build the widgets too. Accomplishing these tasks will require you to perform basically the same steps as before. For this reason, we'll cover the steps to be taken very briefly, and 
will explain only new tasks in detail. If you get stuck with the model or the widgets, you can always look up what to do in previous chapters, namely:


 * <a href="/doc/1_1/practical_accounts_model">Creating the Accounts Model</a>
 * <a href="/doc/1_1/practical_accounts_list">Creating the Accounts List</a>
 * <a href="/doc/1_1/practical_accounts_edit">Creating the Accounts Form</a>


# Creating the Contacts Model
The Contacts model will store the contact details (name, address, and how to reach info) of people you are in dialogue with and will be associated to an account (whether it's a paying customer, or just a lead). The association is done with a relation between the contact model and the account model. We will set this after creating the model.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/contact1.png" rel="prettyPhoto" title=""><img alt="The Account Model" src="/uploads/book/praticalcrm/contact1.png" hspace="5" vspace="5"></a></div> 

1. ***Create "contact" Model*** Click Add Model button from the Model Pane. Name the new model contact and we will be using the same Model Editor like when we created the account model. Below is a list of the fields and data types we want to add. Then remember to click Save afterwards to apply the changes.

<pre>
id				integer
account_id		integer
first_name		varchar
last_name	 	varchar
title			varchar
email			varchar
phone_work		varchar	
phone_mobile	varchar
skype			varchar
msn				varchar
address_line1	varchar
address_line2	varchar
zipcode			varchar
city			varchar
state			varchar
country			varchar
</pre>


# Establishing a Relation

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/contact2.png" rel="prettyPhoto" title=""><img alt="Adding a relation" src="/uploads/book/praticalcrm/contact2.png" hspace="5" vspace="5"></a></div> 

2. ***Adding "account" Relation*** Once your model is created and all the fields are in place, click to the Model Config tab and locate the ***account_id*** field. Change its Type to ***integer*** and size to 11 (important in v1.2). Now double click to its Relations column, then punch the small icon on the right. A panel opens with a listing of your models.

Select the ***Account*** model, this will load its fields into the right pane. Choose the ***id*** field and press OK to close the wizard. Finally, click to the onDelete column, and select ***cascade***.

Don't forget to Save your changes!

By preforming the steps above, you've created a _relation between two models_. The ***account_id*** field of the _Contact_ model is now related to the ***id*** field of the _Account_ model. Such a relation is also called a _foreign key_.

## So what's the point of this?

Thanks to this relation, now each contact person can be linked to a client and naturally, a client may have any number of contacts linked to it. This saves you the trouble of typing in the company name over and over again when adding contacts, that is, _reducing redundant information_ in the database. It also means less errors (no typos). Moreover, when a client gets deleted, all the contacts associated with it will be cleared out automatically as well (the cascade onDelete), again, saving you time and trouble.

But there is much more to foreign keys: they greatly _increase efficiency_ too and allow programs like AppFlower to perform various useful operations quickly and easily that would be hardly possible otherwise. Another example of improvement is when you want to correct an account name, you don't have to find all contacts with the old name and update them (which could be a heavy operation). Instead, this can be done in just one operation by changing the name in the account model and all relations will reflect the change.

Using relations, _your application can do more and can do it more efficiently_, providing faster and better results. The relation we just created is the most simple one. We'll see examples of more advanced relations in the upcoming chapters.


# Creating the List & Edit Widget
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/contact4.png" rel="prettyPhoto" title=""><img alt="The Contacts List Widget" src="/uploads/book/praticalcrm/contact4.png" hspace="5" vspace="5"></a></div> 

Now that we have created the model let's create the contact List, so we can browse and search that data. Again we will use the same methods as we did in <a 
href="/doc/1_1/practical_accounts_list">Chapter 2</a>, while creating the Account list.

3. ***Creating List Widget*** Create a new module and name it ***contacts***. Then launch Add Widget wizard and select ***contacts*** as module location, name it ***listContacts*** and select widget type ***list*** and click Next. Now we just need to add the fields we want to display in our list. Select contact model and choose _id, account_id, first_name, last_name, title and email_ and save.

# Creating the Edit Widget
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/contact3.png" rel="prettyPhoto" title=""><img alt="The Contact Edit Widget" src="/uploads/book/praticalcrm/contact3.png" hspace="5" vspace="5"></a></div> 

Now it's time to build our Edit Widget so we can add and update contact details. There is also nothing new about this you should do the same as in <a 
href="/doc/1_1/practical_accounts_edit">Chapter 3</a>.

4. ***Creating Edit Widget*** Once again click Add Widget, module location is ***contacts***, name it ***editContact*** and widget type is ***Edit***. Then proceed to Next step in the Wizard. Select the ***contact*** model and choose all fields to be included (except the id field). And hit Save.

That was a bit faster this time :-)
