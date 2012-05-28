# Creating the Account Form
Well, we already have a nice list of accounts with all kind of cool features. Now we need a form where we can add new accounts and update the information when needed. For this purpose, we'll have to build an Edit Widget. This will accomplish the aforementioned tasks.

1. ***Add Edit Widget***. In Studio, click the Widgets pane on the left. Click Add Widget button at the bottom to start widget creation. The same wizard starts up that we used to build our List widget. It can be used almost the same way to create an Edit Widget, the differences are outlined below:

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/04_createeditwidget.png" rel="prettyPhoto" title=""><img alt="Widget Settings" src="/uploads/book/praticalcrm/04_createeditwidget.png" hspace="5" vspace="5"></a></div> 

***2. Widget Settings*** The only difference here is that you have to use the Edit widget type instead of the default List. So select ***accounts*** module as Module Location, type in ***editAccount*** as Widget name and choose ***Edit*** as Widget Type. Press Next to continue.


<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/04_addfields.png" rel="prettyPhoto" title=""><img alt="Adding Account Fields" src="/uploads/book/praticalcrm/04_addfields.png" hspace="5" vspace="5"></a></div> 

***3. Widget Fields*** It's the same as in case of Lists, but this time you'll have to make almost all model fields available for your widget, since it has to be able to update all details. Click the ***Account*** model in the left pane, then drag & drop all the fields to the right pane, <u>except for the "id" field</u>. Once you're done, click Save to finish the wizard. Now your widget gets generated and the Widget Designer should appear in a few moments.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/04_preview1.png" rel="prettyPhoto" title=""><img alt="Preview of new Account Edit Widget" src="/uploads/book/praticalcrm/04_preview1.png" hspace="5" vspace="5"></a></div> 

***Preview***. Let's now try to Preview what we have made so far, click the Preview button from the Widget Designer toolbar. You will now see a form, if everything worked our right and you can now start to enter in new entries. After adding new entries, you can close the Preview window again and verify the data has been added by viewing the ***Account Model***.

# Customizing the Form
Our form can now add new accounts and update account details. The layout is nicely arranged, however it still has a kinda default look, so let's customize it a bit

WARNING: Please keep in mind that the changes below ***don't get applied*** automatically!  Press the Save button to save changes to disk!

## Changing the Form Title  
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/04_ititle.png" rel="prettyPhoto" title=""><img alt="Form Title" src="/uploads/book/praticalcrm/04_ititle.png" hspace="5" vspace="5"></a></div> 
4. The form itself has a default title _accounts/edit_, which we want to make more saying. In the ***Widget Inspector*** click the ***i:title*** component and change it's _content property value from ***editAccount*** to ***Account Details***, then press enter.



## Customizing Field Labels  
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/04_fieldlabel.png" rel="prettyPhoto" title=""><img alt="Field Label" src="/uploads/book/praticalcrm/04_fieldlabel.png" hspace="5" vspace="5"></a></div> 

5. The label texts of your form fields are generated from their model field name by default. This we want to change, to make it more informative. Open ***i:fields*** element in Inspector and click to name field. Change the ***label*** attribute's value to ***Company Name***. Do this with the other fields too, to end up with something similar to the screenshot above.



## Automatic Field Recognition and Form Validation is up and running!  
Click the ***i:fields*** entry in Widget Inspector and select the description field. As you can see, its _type_ attribute is ***textarea*** and it appears as a large text box in the form. This is because Studio utilizes ***automatic type recognition***.

AppFlower supports many input types, such as text box, text area, combo box and many others. Basically, all those you can find in modern GUIs are supported. Thanks to the type recognition feature, the type of a form field is automatically adjusted to match the (database) type of data the field is supposed to hold:


***Short textual*** data is rendered as input box
***Numeric*** data is rendered as numbers-only input box
***Long text*** is rendered as text area
***Dates and Times*** are rendered as date pickers
***Relations*** are rendered as combo boxes


This helps you build forms faster. You can change a field's type, but usually you don't have to, since Studio already took care about that upon widget creation.

AppFlower also comes with a very powerful ***input validation system***, which handles user errors with informative messages and makes your forms secure. It supports a wide range of input types, from numbers to dates, strings, file uploads and more. Best of all, this all works without coding, it's fully automated!  

If you look at the selected ***description*** field, you'll see that ***form field validators*** have been attached to it. The reason for this is that Studio automatically adds form validation to all fields and - utilizing the type recognition again - assigns the right kind of validators to them. 


***Numeric*** data can be validated as numbers and ranges
***Textual*** data can be validated as strings with min / max lengths
***Dates and Times*** get date validation
***Relations*** can be validated with existence checks


Besides these, any field can be made ***mandatory***, by setting its validator's _required_ property to true. Such fields ***must*** have a value when submitted. However, all fields are optional by default and when value is provided, the above checks are performed.

## Congratulations! 

Well, that's it. We have successfully configured the basics. It's time to hit the Save button and start up a preview! In a few moments, you'll see all your changes in action! Of course, there is much more to forms: you can create field sets and tabbed forms too, for instance. But no need to rush! This is your first Edit View, so the basics should be enough for now. You'll learn more about these features in the upcoming chapters.

