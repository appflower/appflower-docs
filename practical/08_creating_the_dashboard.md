# Making a Dashboard Layout
A layout is a screen that usually displays ***multiple widgets***. It is a custom view: _you decide what widgets are shown, in what order and how they are arranged_. Even better, these settings can be changed by the users of your application too, and are stored separately for each user. Therefore, layouts allow users to ***customize the view***, to make your application look the way they want to see it!

In many cases, layouts are used to display _overviews_, and that's what we are going to do in this chapter. We'll build a ***Dashboard*** which displays a list widget from each module of the application, thus showing us a summary of what's going on.

## Creating the Dashboard Layout

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/dashboard0.png" rel="prettyPhoto" title=""><img alt="The Layout editor" src="/uploads/book/praticalcrm/dashboard0.png" hspace="5" vspace="5"></a></div>

1. ***Create new Layout*** Click Layout pane. It contains a list of all the existing layouts. There is only one entry in it at the moment, the ***user management*** layout we built earlier. Then hit the Add Page button to create a new layout. Since this will be an overview of our application, name it ***dashboard.xml***, then press enter.

The layout gets created shortly and the Layout Editor shows up. This allows you to add widgets to a layout, arrange them in any way you like and adjust important settings for that view.

NOTICE: Please note, that making modifications to existing layouts works the same way as tweaking new ones, except for "clicking the Add Page button" part. In this case, you should simply double click the given entry to load it into Layout Editor. But other than that, the rest of the steps outlined below can be applied to existing layouts as well. If you've made a mistake while creating the layouts you can right click on the layout in the list and choose ***Delete Page*** to remove it permanently, or ***Rename Page*** to change its name.



## Adding Widgets to Dashboard

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/dashboard1.png" rel="prettyPhoto" title=""><img alt="Adding a widget" src="/uploads/book/praticalcrm/dashboard1.png" hspace="5" vspace="5"></a></div>

2. ***Adding a Widget*** Well, let's start with adding our first widget! Click the Add Widget button at the top. A small panel appears with a list of all your application and plug-in modules.  Inside each module, you'll find the related widgets. Select the accounts -> list.xml widget (the Accounts List) and press the Add Widget button at the bottom of the panel.



The Account List widget now appears in the layout. More precisely, its ***placeholder*** appears, a box representing the widget. When running the application, the widget will be shown in the position where its placeholder is located. If you're unsure about a widget's purpose, press the Preview button under the placeholder. This will render a live preview of that widget.


<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/dashboard2.png" rel="prettyPhoto" title=""><img alt="The Dashboard" src="/uploads/book/praticalcrm/dashboard2.png" hspace="5" vspace="5"></a></div>

That's what it takes, simple huh? You can add other widgets in a similar manner. Let's do that now, add the remaining list widgets too, namely the _Contacts List, Opportunities List and Activity List_, so you can see a full overview.



## Arranging Widgets
We have just added all our list widgets to the layout. However, currently they appear as a stack, simply placed one after another. It would be better to arrange them into columns somehow. 
Also, we might have changed our mind about a widget's position. For example, we might want to see Contacts List at the top instead of Accounts List. Luckily, these changes can be done very easily and it takes only a few moments to arrange everything:

4. ***2 Columns*** Click to Format -> Columns -> 2 Columns. The screen immediately gets divided into two equally wide columns. Currently all widgets reside in the first column, but not for long.

5. ***Re-arrange Widgets*** Grab a widget by ***holding left click***, and move it to the other column. While you're dragging the widget a bordered box appears in various places, indicating possible drop locations. To change a _widget's position_ you do same as when you re-arrange them between columns. Simply drag it over another widget. This will swap them. You can move a widget to any available position inside a column.

NOTICE: The ***Format*** menu contains several other presets as well. You may divide a layout into maximum 4 columns. There are 9 presets in total, each representing a unique configuration. Feel free to explore these! 

6. ***Save the Changes*** Click the ***Save*** button when you're done. This will save your changes to disk.

## Loading the Dashboard Layout

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/dashboard3.png" rel="prettyPhoto" title=""><img alt="Loading the dashboard" src="/uploads/book/praticalcrm/dashboard3.png" hspace="5" vspace="5"></a></div>

When we access the application, we would like to have the Dashboard open as the default view. Since it would make sense to get an overview when accessing the CRM from new.

7. ***Set as Default*** Go to Layouts pane and right click dashboard.xml -> set homepage, then hit the Run button.



Well, that's about it. Once you've saved your layout you can preview it in browser any time, by hitting the Preview or Run button. You'll see a view with all your list widgets appearing, making it easy for your to follow all the CRM activities.
