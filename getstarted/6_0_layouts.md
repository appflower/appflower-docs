# What is a Layout?
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/10_layout_example.png" rel="prettyPhoto" title=""><img alt="Layout Example" src="/uploads/book/layout/10_layout_example.png" hspace="5" vspace="5"></a></div> 

A layout is a screen that usually displays ***multiple widgets***. It is a custom view: _you decide what widgets are shown, in what order and how they are arranged_. 

Even better, these settings can be changed by the users of your application too, and are stored separately for each user. 

 Therefore, layouts allow users to ***customize the view***, to make your application look the way they want to see it!

In many cases, layouts are used to display _overviews_. For example, if your application has user management functions, you probably have multiple widgets to deal with this, such as _"users", "groups", "user rights"_ etc. With a layout, you can display all these widgets on the same screen, making it easy for your users to see what's going on. Such layouts also provide a more responsive and easier to use UI.

# Starting up the Layout Designer
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/0_empty_layout.png" rel="prettyPhoto" title=""><img alt="New Layout" src="/uploads/book/layout/0_empty_layout.png" hspace="5" vspace="5"></a></div> 


Click Layout tab in the left pane. 


The pane now displays a list of _all the layouts_ you have. 

To create a new one, click Add Page button. 

To modify an existing layout, simply double click its name in the list.

Both actions will fire up the Layout Designer, a tool you can use to adjust layout settings and make modifications.

The instructions below can be applied to existing layouts as well as new ones. You must use the same editor and tools in both cases.

NOTE: Please ***save your changes frequently*** while working with the Widget Designer! Some of its functions will take you to other parts of Studio and without saving, ***your changes could be lost***!


# Choosing Layout Type - Normal or Tabbed
First of all, you have to decide ***what kind of layout*** you wish to create.:

 A Normal layout has a ***single*** content area, all widgets will be placed here.
 A Tabbed layout consists of one or more "tabs", ***each*** having ***its own*** content area.


<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/06_change_to_tab_layout.png" rel="prettyPhoto" title=""><img alt="Tabbed Layout" src="/uploads/book/layout/06_change_to_tab_layout.png" hspace="5" vspace="5"></a></div> 

Tabs are useful when your layout contains many different widgets. Placing all those widgets in a single content area works, but it's not very user friendly. Looking at 10 widgets may be confusing for the users..

Sometimes it's better to ***categorize*** your widgets with tabs, making navigation way easier.

For example, imagine a simple application that has 4 widgets: _product list, edit product, vendor list, edit vendor_. It's better to create 2 tabs in this case: ***"Products"*** and ***"Vendors"***, and place each widget in the appropriate tab.
    
<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/07_adding_a_tab.png" rel="prettyPhoto" title=""><img alt="Adding a Tab" src="/uploads/book/layout/07_adding_a_tab.png" hspace="5" vspace="5"></a></div> 

Choose a type from the menu Format -> Type.

 If you picked "tabbed", a new tab appears whose name will be the same as the name of your layout. Let's change this default name to something more meaningful now. 


The following functions are always available for tabbed layouts:


1. Rename a tab: You may change the title of a tab by right clicking it and choosing the option Rename Tab.

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/08_tabs_with_columns.png" rel="prettyPhoto" title=""><img alt="Tabs with Columns" src="/uploads/book/layout/08_tabs_with_columns.png" hspace="5" vspace="5"></a></div> 

2. Create new tab: Should you need more tabs, you can add as much as you like, using Format -> Add new tab function.


3. Remove a tab: Finally, you may of course delete any tab by pressing the ***small X*** (close) button in tab title.

# Adding Widgets to Your Layout

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/01_add_widget.png" rel="prettyPhoto" title=""><img alt="Add Widget Selection" src="/uploads/book/layout/01_add_widget.png" hspace="5" vspace="5"></a></div> 

Your new layout is empty at the moment, let's add some widgets to it! 

Click Add Widgets button. This opens the ***Widget Selector***.
    
A list appears which contains all widgets located in your main application (frontend) and the installed plug-ins. 


To add the desired widget to your layout, either double click its name or just select it and press the Add Widget button at the bottom of the list.

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/02_first_widget.png" rel="prettyPhoto" title=""><img alt="Adding a Widget to Layout" src="/uploads/book/layout/02_first_widget.png" hspace="5" vspace="5"></a></div> 
    
The ***placeholder*** of the widget now appears in the layout. Each placeholder comes with 3 important functions: 

The Edit button allows you to load the given widget into Widget Designer and make changes. 

The Preview button loads the widget in the browser to show you how it looks like. 


The X button (in the top right corner) removes the widget from the layout.

<div style="clear:both;"></div>    
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/09_advanced_layout.png" rel="prettyPhoto" title=""><img alt="Multiple Widgets and Tabs" src="/uploads/book/layout/09_advanced_layout.png" hspace="5" vspace="5"></a></div> 
    
Repeat the above steps for each widget you wish to add.

NOTE: Please note that ***it is possible*** to ***add the same widget multiple times***. This is useful when you want a widget to be displayed in multiple tabs, for example.
    
# Customizing Content Areas - Columns
Regardless of the layout type, the widgets are simply listed one after another at the moment. Sometimes it's a better idea to divide the content area into 
***multiple columns*** to arrange your widgets in a better way. 


If you're working with tabs, ***select a tab*** now.
    
<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/04_format_columns.png" rel="prettyPhoto" title=""><img alt="Formatting Columns" src="/uploads/book/layout/04_format_columns.png" hspace="5" vspace="5"></a></div> 

Hit Format -> Columns for a list of options. 


You can create up to ***9*** columns. The presets offer the most commonly used arrangements. 

Choose one of the available options now. 

This immediately changes the structure of the layout. Now you have multiple columns. 

Widget Location: To move a widget into a _different column_, simply drag its placeholder to the desired location.

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/layout/05_arrange_widgets.png" rel="prettyPhoto" title=""><img alt="Arranging Widgets" src="/uploads/book/layout/05_arrange_widgets.png" hspace="5" vspace="5"></a></div> 
    
Widget Position: You may also change the position of a widget _inside a column_. Just drag it to an other widget, they will be swapped.
    
NOTE: Please note that you ***cannot*** place widgets just anywhere. While moving them around, a ***box with a dashed border*** indicates the possible locations.

<div style="clear:both;"></div>
In case of tabbed layouts, you have to do this on ***each tab*** separately.

Well, that's about it!  Now your layout is ready to use.

To see it in action, click to the Preview button. This loads it in a new browser window.
