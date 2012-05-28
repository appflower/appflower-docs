# Designing Edit Widgets
In order to complete our ***Music Catalog*** mini application, we need to create an _Edit widget_.


We already have a List widget, which displays a nicely organized list of our songs. The Edit widget will allow us to update any of the song records or create new ones. It will also let us view the details of a particular song.

# Edit and Show Views - Same Same, but different -:)

The Edit and Show widget types are quite similar. In fact, the Show view is _almost_ the same as a standard Edit view, the only significant difference (for you, at least) is how the the information is displayed.: 

Edit widgets are ***interactive forms*** with the ability to change the stored information, whilst Show widgets are ***non-interactive***: you can see it all, but you can't touch anything! Another difference is that a Show view usually contains all details of a record, while the Edit view shows only some parts, those that the user is allowed to change.

There are some other differences as well, but those are important for the AppFlower engine only. Anyway, what you have to keep in mind is that the characteristics of these views are _almost the same_. You can use the same editor to build them, and their settings are nearly incidental. 

For this reason, the section below covers ***both of them***. Even though we're going to create only an Edit Widget in the next few steps, you could perform the same steps to add a Show Widget.

# Creating the Widget

This is very easy, since you can use the wizard you've built your _List Widget_ with. Basically, you have to perform the same steps, with some minor differences: Click Widgets in the left pane, then hit the  Add Widget button to start the wizard.

Then select ***musiclib*** as the module to place your widget in. Choose the proper widget type, Edit or Show, according to what kind of widget you wish to build . Click Next to continue. Select the ***Song model*** from the list.

Move the fields you want to use in your widget to the selection area***. In present case,  we need all the of them (_title, genre, author and location_). And click Save to finish.

Once the widget is generated, the Widget Designer loads up.

# The Widget Designer

A familiar view appears... Yes, this the same application you used for building the List widget. It offers tools you already know:

<div class="image_medium" style="float:right;"><a href="/uploads/book/widget/05_edit_widget.png" rel="prettyPhoto" title=""><img alt="Edit Widget" src="/uploads/book/widget/05_edit_widget.png" hspace="5" vspace="5"></a></div> 

The left pane of the Widget Designer shows a ***live preview*** of your widget, much like the one you saw when you've worked on your List.


This time, however, it displays _form fields_ instead of columns.  


The right pane contains the Widget Inspector, which shows a very familiar looking tree structure. Indeed, you've already encountered with most of those components, but some of them work in a slightly different way now and there are a few new ones, too.

# The Widget Inspector
The components of an Edit / Show view are listed in the Widget Inspector's tree. Let's see them one by one:

## Actions

These are the same as the ones you used in your List widget. The only difference is that the buttons will be placed ***at the bottom*** instead of the top. Of course, you can create as many actions as you wish.

## Datasource

This sounds familiar as well.. Its settings, however, are slightly different in case of Edit / Show widgets. But no worries! _Studio already configured this one for you!_ The default settings should be good for basic widgets, including the one we're working on now. If you wish to learn more about data sources, please see
<a href="http://www.appflower.com/doc/1_1/reference_edit_datasource" >Reference Manual  (Data sources)</a>

## Fields

In Edit / Show widgets, this represents the ***global settings of the form***. There are various properties you can tweak, but you don't have to, since all of them are optional. The default values are already in place and should work fine in most cases. 

However, there are some useful settings that you may have to change occasionally. We'll have a look at these below. The rest of the options can be found in the
 <a href="http://www.appflower.com/doc/1_1/reference_edit_view" >Reference Manual (Edit View)</a>.

Action : This is a widget URI. It should point to the _Symfony Action_*** which will process this form***. You don't have to define this, unless you wish to use a custom action. Studio configured it for you already, it points to some generated code which will work just fine with your widget.

Label Width : The ***width of the label text***  of a form field, measured in pixels. If you use long field names, you may have to change this. It applies to all form fields globally.

Multipart : You should enable this if your Edit widget is supposed to ***upload files***.

Redirect : The value is an URL. This is where the user will be ***redirected*** upon successful form submission.

Submit Label : The ***label text*** of the _Submit_ button.

Reset Label : The ***label text*** of the _Reset_ button

NOTICE: : It's good to know: You ***don't*** have to run the widget wizard again to add ***another field*** to your form! Just right click on ***Fields***, then choose Add Field option.  Now you can click to the newly added field to adjust its settings.

## Field

You've seen something like these before. In List Widgets, these are called "columns", since they represent the columns of the list. Now they stand for the ***fields of the form***. They have many useful optional settings and also 3 mandatory ones. Let's have a quick look at these:

***<u>The mandatory properties</u>***

Name : the ***database name*** of the form field. ***You should never change this***.

Value Source : Where does the ***value of this form field*** come from? When you create a new record, the form is empty, you'll have to fill in the details. However, when you're updating an existing record, many (or all) of the fields will be already filled using the data stored in the data source.

This property allows you to define exactly how would you like that data to be retrieved. There are several ways, but we'll discuss only one for now (see below). This is the _default_ way, and should work fine with most Edit / Show widgets. The rest are more advanced topics and you'll need them only later.  To learn more about those, please consult 
 <a href="http://www.appflower.com/doc/1_1/reference_edit_field_value" >Reference Manual (Values)</a>.

<u>The "Source" setting</u>

It means that the value of this form field should be fetched using the ***related property of the Model***. So for instance, our Music Catalog model has a property called _"Author"_ which holds the name of an artist. Subsequently, the "Author" form field will use the _Author_ property of the model to fill in the artist's name. 


***Make sure*** that the Value Source property is set to ***"source"***.
	
Value type : This controls how the system should access the source we described above. This is an advanced topic, and therefore you shouldn't mess with it. Studio already selected the right value for you. For for further details, please check
 <a href="http://www.appflower.com/doc/1_1/reference_edit_field_value" >Reference Manual (Values)</a>



***Make sure*** that the Value Type property is set to ***"orm"***. 

***<u>The optional settings</u>***

Label : The ***text*** that appears on the left side of the form field. This describes the purpose of the field.

State : The ***state*** of the form field. A field is interactive by default: people can read and change its contents. 


The ***readonly*** state prevents a user from changing the content.


The ***disabled*** state makes the field inactive.: its value cannot be modified and it will be rendered differently. Also, the system ignores the value of disabled fields when the submit button is pushed.

Style : a ***CSS class name*** goes here. You can use this to change the appearance of the field. 

Type : This is actually a mandatory property, but _Studio will always fill it automatically for you_. The type determines ***what kind of form field*** should be rendered. A text box? A button? A large text area? AppFlower supports all those types you can find in HTML and several special ones too.

Since Studio sets this for you in an intelligent way, normally you don't have to tweak it. If you really have to change the type, you can read more about the available options in 
<a href="http://www.appflower.com/doc/1_1/reference_manual" >Reference Manual (Types)</a>.

## User Input Validation

When the form gets submitted, you have to find out somehow if the user filled all those fields correctly. With AppFlower, this is easy, since it comes with ***automatic form field validation***.

All you have to do is to attach one or more ***validators*** to your form field, and AppFlower will take care about the rest: it checks the submitted data, and in case of an error, it displays _nicely formatted messages_ for the user.

AppFlower supports all ***Symfony 1.2+*** validators. If you're familiar with Symfony, but need more info, please consult the <a href="http://www.symfony-project.org/gentle-introduction/1_4/en/10-Forms" >Symfony documentation (Chapter 10 - Forms)</a>. In every other case, please see <a href="http://www.appflower.com/doc/1_1/reference_edit_field_validator" >Reference Manual (Validators)</a>.

For now, we suggest you to use the Symfony's built-in validators only, as these should cover most needs. To add a validator, right click the Validators entry under the field name and select Add Validator.  Click the new validator entry to fill in its name.

If the validator takes ***parameters***, you can add those as well:  Right click the validator name and select Add Parameter. Fill in the Name and Value properties of the parameter.

# More on Forms

This chapter deals with the basics of Edit Views and is trying to give you an overview, since that's just enough for your first edit widgets. For this reason (and also for keeping this book as small as possible)  advanced concepts and some features won't be discussed here. But of course, feel free to explore more:


 * <a href="/doc/1_1/cookbook_fieldsets" >Field-sets and Tabs in Forms</a>
 * <a href="/doc/1_1/cookbook_floating" >Horizontally Aligned Forms</a>


Well that's it! You've successfully created your first Edit / Show Widget, congratulations! To see it in action, press the Preview button.