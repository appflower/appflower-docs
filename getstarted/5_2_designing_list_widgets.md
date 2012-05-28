# Designing List Widgets

We have successfully created a List widget in the previous chapter. That widget is already fully operational: it can list your records and perform various useful operations (such as paging, export etc). In fact, you could load it in your browser and start using it right now!

This applies not only to Lists, but _all kind of widgets_ built with Studio.: once they have been generated, they are ready to use. However, such a widget is _not perfectly finalized_: it has a default look and its settings aren't customized either. 

Therefore, you'll probably want to adjust at least some of the widget settings to make it better fit your needs. You might also want to enable certain advanced widget features, which are disabled by default. In order to make these changes, you'll have to use another Studio tool, the Widget Designer.

# The Widget Designer
<div class="image_medium" style="float:right;"><a href="/uploads/book/widget/04_widget_designer.png" rel="prettyPhoto" title=""><img alt="List Widget (displayed in Widget Designer)" src="/uploads/book/widget/04_widget_designer.png" hspace="5" vspace="5"></a></div> 	

Open the Widget Designer by clicking the  Widgets button in the left pane. Select the ***musiclib*** module, and double-click on your ***list widget*** to start up the editor.

This tool has 3 tabs. Currently we are working with basic features (i.e.: without doing any custom coding), so ***you need only the first one***. You can safely ignore the other two for now. If you wish to learn more about those, please see the <a href="/doc/1_1/devbook" >Developer's Book</a>.

# Modifying List Appearance

The Widget Designer is the currently active tab. This shows a ***live preview*** of your widget. In fact, it's almost the same as the browser version, it just doesn't display the data. 

As you can see, the list consists of those columns you've just added using the wizard. They are ordered alphabetically by default.  If this is not what you want, you can reorder them very easily.: To change the order of the columns, simply ***drag them to the right position***. This will swap the given columns. 

Press Save button to save your changes.
	
# The Widget Inspector
A List widget may have several additional components besides its columns, such as various _links and buttons_ that perform certain operations. The columns themselves also have numerous properties to _customize the view_ or _toggle advanced features_. 


The Widget Inspector (in right pane) is a tool that allows you to do all this stuff and more. It displays all widget components and their settings in a tree-like view.

To ***edit the settings*** of a component listed in the Widget Inspector, simply ***click its name***. This loads the related settings into the small area below the right pane. A list of name - value pairs appears. You may adjust any of these settings by changing the corresponding value. 

The ***mandatory settings are listed at the top***. The rest are optional, so you don't have to tweak them if you don't want to. Your changes will immediately appear in the live widget preview (left pane) 

Don't forget to use the Save button frequently!  Your changes won't be saved automatically.

# Components of a List Widget

The section below will introduce you to the most commonly used List components and their basic settings. These are enough to create basic or novice applications. The rest of the settings are kinda advanced, thus we suggest you to ignore them for now.  Detailed descriptions of all the available components can be found in the <a href="/doc/1_2/reference_manual" >Reference Manual</a>

So let's see those things listed in Widget Inspector, one by one (from top to bottom):

## music/list [list]
This is the first component. It is always named after module and the widget you're working with. It contains some useful general settings.:

maxperpage This controls the _maximum number of records_ to be shown on a list page. The List may have any number of pages, this makes it able to handle large number of records efficiently. The default value is 10. To add params inside Studio, like adding maxperpage to control the amount of entries being shown on a page you can use the following steps.

<pre class="brush: plain">
1) Right-Click in Widget Inspector on the root-node. Click add i:params
2) Right-Click on i:params and add an i:param
3) Set name to maxperpage, the attribute we want to adjust, and set the _content to the amount of entries per page like 25.
</pre> 

Title This is the title text of the list. It can be anything you like.

Change this to ***Music Library***.
	
## Actions
<div class="image_medium" style="float:right;"><a href="/uploads/book/widget/widget-toolbar-action.png" rel="prettyPhoto" title=""><img alt="List Widget - Toolbar Actions" src="/uploads/book/widget/widget-toolbar-action.png" hspace="5" vspace="5"></a></div> 	
These are toolbar actions placed at the top of the list. Basically, ***they are links*** pointing to other _widgets, layouts, or external resources_ (like a website). Their main purpose is to interconnect the related parts of your application, but any kind of URL is supported. Of course, you can add multiple actions to your widget.
NOTICE: : Actions can be much more than just links. They have many additional features that you'll find useful. You can learn more about the full power of actions in the
<a href="/doc/1_1/reference_action" >Reference Manual (Actions)</a>


<pre class="brush: plain">
 Name: Product List
 Url: products/list
 Icon Url: /images/products.png
</pre>

To add a new action, right click on i:actions, then choose Add Action from the context menu. The three most important settings of an action are:

Name: This is the ***label text*** of the button.
Url: This is where the ***action will point to***. If you want it to point to a _widget or layout_, use the internal URI format (module_name/action_name) 
Icon Url: This should be a ***path to an image file***, which will be attached to the button as an icon. It is optional, leave it blank and no icon will be shown.

## Datasource

Every List has a data source, that's where the records are coming from. The Widget Creator Wizard configures this one automatically, so usually you don't have to change its settings. This is an advanced topic, if you want to learn more about data sources, consult 
<a href="/doc/1_1/reference_edit_datasource" >Reference Manual (Data sources)</a>.

## Fields

<pre class="brush: plain">
 Exportable: true
 Pager: true
 ...
</pre>

It contains some important general settings to control the appearance of the list and its various features. Like the previous one, it already has a configuration suitable for most List widgets, so you don't have to change anything. But if you insist, some of the most important properties are:


Exportable: If it's enabled, controls will be added to allow the list to be ***exported as CSV***. It is an undoubtedly useful feature, since it allows users to import your data into tools like MS Excel. 

Pager: If it's activated, the ***list will be page-able***, otherwise only a single page will be displayed. 
Selectable: When activated, small checkboxes will be added to each list row. The _selected rows then can be posted_ to the server for processing. This is another neat feature, since it ***makes the list act like a form***. The _MoreActions_ component may also make use of this selection (see below). 
Action: A widget URI to post the selected items to. It must be used with Selectable. 
Tree: When it's on, the ***list will be rendered as a tree *** instead of the traditional table stuff. This requires some special input though, for more information, please see <a href="/doc/1_1/reference_list_view" >Reference Manual (Multiple kind of Lists)</a>.


## Columns

<pre class="brush: plain">
 Name: first_name
 Label: First Name
 Resizable: true
 Hidable: true
 ...
</pre>

The columns are listed under the _Fields_ component. These are the columns of your list and they have many settings to control their appearance and behavior. The first two are: 
Name: The ***database name*** of the column. ***You should never change this***. 
Label: The ***title text*** of the column. The default value is constructed from the system name. You'll probably want to replace this with something better.


The rest of the options are already set, and should be good in most situations. Some of the more interesting ones are: 
Align: It controls how the text in the column should be aligned. Left, right or center? The default is "left". 

GroupField: The system name of a column goes here. If you fill this, the items in ***the list will be grouped by this column***. This is very useful sometimes, just think of a list of products with categories.. 

Resizable: This allows users to freely ***resize the column***.  You should always enable this . 
Sortable: It allows people to ***order the list*** by the given column. It's enabled by default.
Width: The default width of the column (in pixels), which can be changed later by resizing.
Style: A ***CSS class name*** goes here. This way, you can _customize the appearance_ of the column (for example: set a different background color etc)
Qtip: This is a boolean value, set to "false" by default. When set to "true", the value of the corresponding list cell is shown in a bubble (on mouseover). This is useful when you need to store a long value in limited cell space; thus, it makes those long lines readable without damaging the list structure.
Hideable: When it's turned on, ***users can hide the column*** with a single click. Comes handy sometimes. For example, in lists with many columns it makes easier to find what you're looking for.
	
## MoreActions
These are also actions, but of a different kind. They appear in the ***More Actions*** menu, which is added automatically to every list. These actions operate on the ***selected list rows*** and can _post this selection to the server_ for processing. If the list doesn't support selections (see Fields), they act like normal actions, however - since they are located in a drop-down menu - it's easier to add many of them.

 A very common use of MoreActions is an operation that must be performed on _all or some of the records_. For example: in a User list, there could be a MoreAction to Activate / Deactivate the selected users.. and so on. They have the same settings as normal actions.

## RowActions
Another kind of Action. These are attached to ***each row of the list***, in the form of small icons. They are always _related to a single record_. The RowAction URL contains the ID of the related record (list row). 

For instance, a possible use-case is again a User list. RowActions will point to the Edit User page as well as to the Delete User function. These also have the same settings as normal actions.
