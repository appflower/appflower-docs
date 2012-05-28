# Creating the Account List
Now that we have a working model with some data, it's time to create our first two widgets. These will allow us to manage our data: list all the accounts in various ways and to add and/or update records. We'll start with List Widget.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/03_newmodule.png" rel="prettyPhoto" title=""><img alt="New Module" src="/uploads/book/praticalcrm/thumb/03_newmodule.png" hspace="5" vspace="5"></a></div> 

1. ***Create "accounts" Module***. In Studio, click to Widgets in the left pane. A list of currently available ***modules*** appears. These are a bit like _folders_, they store widgets in a nicely organized way. First of all, we'll have to create a new module, to store all those widgets related to clients. Click the Add Module button at the bottom. A new entry appears in the list with the temporary name "NewModule". Change this to ***accounts*** and press enter. This generates the module. 

2. ***Launch Widget Builder***. Click the Add Widget button which can be found in the  Widgets sidebar to start the Widget Builder wizard. This tool can build any kind of widget for you quickly with it's two easy steps.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/03_listwidgettype.png" rel="prettyPhoto" title=""><img alt="Widget Settings" src="/uploads/book/praticalcrm/03_listwidgettype.png" hspace="5" vspace="5"></a></div> 

3. ***Widget Settings***. In the first step we can set some general settings for our Widget which we are going to build. Basically, here you'll have to name your widget and select its location and type. Select the newly created ***accounts*** module as Module Location, name the new widget ***listAccounts*** as Widget name and assure the Widget Type is of ***List***. Then press Next to continue.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/03_listwidgetfields.png" rel="prettyPhoto" title=""><img alt="Widget Fields" src="/uploads/book/praticalcrm/thumb/03_listwidgetfields.png" hspace="5" vspace="5"></a></div> 

4. ***Widget Fields***. In the second step we will associate Model fields to the widget. You must choose a model and select the parts which you want to use in the Widget. So to build our List of Accounts, we want to associate the _Account_ model to our new Widget. Let's start by selecting the _Account_ model in the left pane. This loads the model's fields to the middle pane. Now drag & drop those fields you want to be used to the right pane. Since this is a List Widget, we don't need all the details and it's enough to move _id, name, city, country and phone_ for now. Once you're done, click ***Save*** to finish the wizard.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/03_widgetdesigner.png" rel="prettyPhoto" title=""><img alt="Widget Designer" src="/uploads/book/praticalcrm/thumb/03_widgetdesigner.png" hspace="5" vspace="5"></a></div> 

That's it! Now your widget gets generated and a new view should appear in a few seconds. This tool is the Widget Designer and allows you to customize further details of the widget. This we will look more into in a later chapter, for now let's check out what we have made so far. Click on the Preview button found in the Widget Designer toolbar. This should open up a preview mode of the list widget, like what the users would see.

# Customizing List Appearance
At this point, your list widget looks nicely organized and is fully operational. It has informatively named columns and is page-able too, so it can handle large amount of records efficiently. Now we're gonna have a look at how to change a few more attributes to make our list even better.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/accountlist3.png" rel="prettyPhoto" title=""><img alt="Widget Inspector" src="/uploads/book/praticalcrm/accountlist3.png" hspace="5" vspace="5"></a></div>

To customize the List appearance we can use the ***Widget Designer***  and Widget Inspector. The Widget Inspector is available on your right in the ***Widget Designer***. Using the Widget Inspector we can change the parameters of how different functionality of a Widget works. And the Widget Designer allows you to re-arrange and view how your current configuration will look like. The Widget Inspector contains all the components of the widget and displays them in a tree structure. Basically, you enable or disable features and change most of the settings by changing the properties of these components. Let's have a look on a few settings to change.




NOTICE: The Widget Designer is accesible after creating the widget and will open automatically. You can also open saved widget, by double clicking on it under Widgets in the left pane.

## Arranging Columns
In the left pane of the Widget Designer you should see a _live preview_ of your widget. All the changes you make will be immediately reflected here. As you can see, the columns of the list appear in a default order and their titles are identical to the names of the model fields. Let's change this now:

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/accountlist1.png" rel="prettyPhoto" title=""><img alt="Changing Column Title" src="/uploads/book/praticalcrm/accountlist1.png" hspace="5" vspace="5"></a></div> 

5. ***Re-order the columns***, simply drag a given column over another, this will swap them. Move the columns to the right positions to make the list look better. A possible scenario can be seen on the screenshot.

6. ***Change column title***, click on the ***name*** column title, which then gets transformed into a text box. Now type in ***Account*** and press enter. The column title will be changed instantly. 



## Changing the Widget Title  

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/accountlist2.png" rel="prettyPhoto" title=""><img alt="Changing Widget Title" src="/uploads/book/praticalcrm/accountlist2.png" hspace="5" vspace="5"></a></div> 

7. ***Change Widget Title*** Our list have a default title, which should be replaced. Click the ***i:title*** component in the inspector, the related settings now appear in the box below. This item has only one property, __content_. Change its value to ***Account List*** and press enter. The title of the list gets immediately replaced in the live preview.

## Automatic Filters and Sorting are already in place! 

If you click to the ***i:fields*** element in Widget Inspector now, you'll see that its _remoteFilter_ and _remoteSort_ properties are set to true. This means that the list is already ***sortable and search operations can be performed too***! All List widgets generated by Studio have this ability by default: you can order or filter the results by <u>any column</u>. 

***Sorting by a column*** can be done by clicking the _column title_. This toggles ascending and descending modes.

***Filtering by a column*** can be triggered by clicking the _small arrow in column title_ then choosing Filters. Each column has filter that fits its database data type.:


***Textual*** columns get a keyword search box
***Numeric*** ones operate with ranges
***Dates and Times*** get a date picker 
***Relations*** are filtered using live-search combo boxes.

It is possible to apply several filters at the same time and  you may clear all active filters via More Actions -> Filters -> Clear current filter option.

Click to ***i:fields*** and select one of the columns to see what filter is applied to that column. This is controlled by the _filter_ attribute. You may change its value, but in most cases you don't have to, since Studio automatically sets up the best filter for you.

To turn of sorting or filters set the _remoteSort_ or _remoteFilter_ parameters of ***i:fields*** to false.

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/03_previewlist.png" rel="prettyPhoto" title=""><img alt="Widget Preview" src="/uploads/book/praticalcrm/thumb/03_previewlist.png" hspace="5" vspace="5"></a></div> 

## Congratulations!  

Once you've done all these, press the Save button, to save your changes to disk. You may hit the Preview button now to see your widget in action!

WARNING: You should ***always*** save before launching a preview. Only saved changes are reflected!

Congratulations! You have just created a fully functional and powerful List widget. By completing this small tutorial you've built a widget that is able to: list your data in a page-able manner, refresh data, sort or filter your data in various ways, hide/show columns, columns are resizable, and you can export the results as CSV. But it doesn't stop here, you can also build a PDF report for printing. Not bad huh? -:)

In the next chapter we'll complete our client management tool, by adding an equally powerful Edit view to it.
