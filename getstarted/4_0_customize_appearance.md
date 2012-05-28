# Application Themes
The Theme Designer a tool made to customize your Application look and feel. By choosing one of the pre-defined theme skeletons and with the possibility to further customize the visuals of that theme.

<div class="image_medium" style="float:right;"><a href="/uploads/book/theme/theme_designer_selector.png" rel="prettyPhoto" title=""><img alt="Theme Selector" src="/uploads/book/theme/theme_designer_selector.png" hspace="5" vspace="5"></a></div> 
You can start up the Theme Designer from menu button. A pop up opens with two tabs. Where you will see two tabs Theme Selector and Editors

# Theme Selector
This is where you choose a theme, or in other words, a way your application should be presented. For now, there are two options here: Viewport and Desktop.

The Viewport theme is the default setting. If you choose this, you'll end up with a traditional view, something like most modern web applications you've seen so far.:  The application "window" will fill the content area of the browser completely. The application menu will be placed on top, just like in any Windows program.

The Desktop setting is kinda more innovative and will make your application appear like a graphical OS, for example Windows. A nice desktop will be created for you, where links to the most important parts of your application can be placed. These will appear as icons. The main menu will be turned into a Windows "Start menu" like thingy.

Which one to choose is merely a question of taste. Both are well known views, most people out there are already familiar with them. The Desktop view offers more eye-candy and perhaps an easier
navigation, but the traditional one is straightforward and easy to use as well. 

***How-To change a Theme***
1. Make your choice and press Set Theme button. You can change this setting later, so no worries. That's basically it, now the theme layout has been reflected in your application.
2. You might want to customize the Theme, changing colors, adding icons and links This can be done from the Editors tab.


# Editors
<div class="image_medium" style="float:right;"><a href="/uploads/book/theme/theme_designer_editors.png" rel="prettyPhoto" title=""><img alt="Theme Editors" src="/uploads/book/theme/theme_designer_editors.png" hspace="5" vspace="5"></a></div> 
Currently there are 3 available editors for the Theme(s), CSS, Start Menu and Desktop Link editor. The first one allows you to modify Studio look and feel, the other two are useful for applications with a Desktop Theme.

# The CSS Editor
<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/theme/theme_css_editor.png" rel="prettyPhoto" title=""><img alt="Theme CSS Editor" src="/uploads/book/theme/theme_css_editor.png" hspace="5" vspace="5"></a></div> 
This tool lets you customize Studio appearance by changing various CSS style rules. Yes, this is the same CSS you use to build "normal" web pages. If you open the editor, you'll see a bunch of CSS files on the left and the editor window on the right. Here is a small summary of all the available stylesheets

afStudio.console is Studio Console specific rules. 
afStudio is the main CSS file for Studio. **This is where all the icons, colors and main style rules can be found.** These rules are for Studio interface as well as all Studio tools.
afStudio.tplSelector is a few rules for Theme Designer popup.
prettyPhoto is the CSS for PrettyPhoto lightbox image renderer. This is a third party component, you shouldn't tweak it!
welcome is the rules for the welcome screen (shows up when you start Studio).

You may edit any of these files using the built-in editor. When you're ready, press Save button to save your changes. Any modification should be reflected immediately after page reload. To make sure you see the most up-to-date version, you should turn off caching in your browser or force full reload (CTRL+SHIFT+R under Windows or COMMAND+SHIFT+R for Mac users).

Regarding design changes, it is also good to know about the directory web/images/famfamfam. This can be found in all AppFlower packages, and it holds hundreds of high quality icons. This will come in handy for Studio customizations as well as building start menus and desktop links (see below). Whenever you need a new icon, look here first!

NOTE: Caution! Modify any of the CSS files only if you know what you're doing! Mistakes can cause problems in your Studio interface and may result in broken design! 
If you're not familiar with CSS yet, but you're eager to customize, you can learn more from <a href="http://w3schools.com/css/default.asp">http://w3schools.com/css/default.asp</a>. This is short and very well written introduction on CSS (Cascading Style Sheets). You should read this at least before modifying anything!

Once you've finished CSS tweaking, go back to the Editors tab. We're gonna have a look at the other 2 editors now.

NOTE: Did you know that you can switch back to the Theme Designer panel from any editor, by hitting the small Theme button in the top right corner? Try it now!


# Start Menu Editor
<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/menueditor.PNG" rel="prettyPhoto" title=""><img alt="Start Menu Editor" src="/uploads/book/praticalcrm/menueditor.PNG" hspace="5" vspace="5"></a></div> 
If your AppFlower application uses the Desktop theme, you can use this editor to add items to the Windows-like start menu (located in the bottom left corner of the desktop).

Have a look at the tool located on the right side of the view. It has two tabs, ***Menu*** and ***Tools***. We'll begin with the first one. It's a bit similar to the Widget Inspector: lists all items of the Start Menu as a tree structure. Currently there are two items there: the ***Menu***, which is the root item, and a default item that points to the project dashboard.

## Adding new menu items

To ***add a new menu item***, simply right click to Menu -> Add -> item. A new node appears and its properties are being displayed in the box below.

***To edit an existing item***, just click its name, its properties will be loaded immediately

label  The title text that should be displayed in the menu. For example: _My Item_
name A ***unique name*** to identify the item. This won't be displayed anywhere, but the system needs it. Names like _item1, item2_ and so on will always do.	
type Is it an ordinary item or button? It specifies the type of the item. We'll discuss shortly (see buttons below).
urlThis should be a ***widget or layout*** URL the item should point to, for example: _/mymodule/mywidget_ .

There are also two optional attributes. You may leave these blank if you want them to be ignored.

icon A path to an image file goes here, which will be attached to the item as an icon: _/images/famfamfam/accept.png_ .
tooltip Some text to be displayed when moving the mouse pointer over the item, for example _A helpful hint_ .

<p class="warning">Did you know that a huge selection of icons is shipped with AppFlower? You can find hundreds of them in ***/images/famfamfam***

## Button: a different kind of menu item

Whether you you're creating a new item or a sub-menu entry, it is always possible to right click MenuItem -> Add -> button. This will create another kind of entry, which has almost the same characteristics as a normal menu item, but instead of ***url***, it has a ***handler*** attribute. The value of a handler is ***custom JavaScript*** code, allowing you to make a button perform additional actions. For instance, the value below  loads a widget only if user confirms some choice:

<pre class="code">
if(confirm("Are you sure?")) afApp.load("/mywidget", "mymodule");
</pre>

NOTE: Just like menu item, buttons also can be used in sub-menus.

## Creating sub-menus

This can be done the same way you create "normal" menu items, but you should add the new item to the desired entry instead of the root node. So for instance, assuming you have an tem called "Myitem" in your menu, you could right click MyItem -> Add -> item. This will insert a new node under MyItem. This can be also turned into a sub-menu later and so on. This way you can build a start menu with an number of levels.

## Adding Tools

Click to the ***Tools*** tab at the top. The same tree view appears as in Menu tab. However this one let's you add "tools" by right clicking the root ***Menu*** node, so like Menu -> Add tool.

Tools are also links pointing to widgets or layouts, like menu items, but they will be displayed in the black area on the right. This has limited space, so you should put your most frequently used links here. They have the following attributes:

name A ***unique name*** to identify the item. This won't be displayed anywhere, but the system needs it. Names like _item1, item2_ and so on will always do.	
text The title text to be displayed, such as _My tool_
urlThis should be a ***widget or layout*** URL the item should point to, for example: _/mymodule/mywidget_ .
iconCls This is an optional attribute, the name of a CSS class goes here that should be defined in ***main.css***. It allows you add custom look. An example could be: _mytoolclass_ .

<p class="note" >Unlike menu items and buttons, tools can be added only to the root level, it's not possible to build sub-menus here.

# Shortcuts Editor
<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/shortcutedit.PNG" rel="prettyPhoto" title=""><img alt="Desktop Link Editor" src="/uploads/book/praticalcrm/shortcutedit.PNG" hspace="5" vspace="5"></a></div> 
The Shortcuts Editor allows you add links (as icons) to your application desktop. Just like the previous one, this editor is useful only for application is using the Desktop theme. Usually these links point to common used functions such as layouts or frequently used widgets, but of course feel free to link anything you like -:). 

The tool is is very similar to the Start Menu builder. Basically, you can use it the same way, but in this case you obviously won't be able to add nested items, since it wouldn't make sense.

## Adding desktop shortcuts

***To add a new shortcut***, right click to the root node Menu -> Add link. A new item appears immediately, having the attributes described below.

***To edit an existing shortcut***, just click its name, its properties will be loaded in a second.

name A ***unique name*** to identify the item. This won't be displayed anywhere, but the system needs it. Names like _item1, item2_ and so on will always do.	
title The title text to be displayed, such as _My Widget_
urlThis should be a ***widget or layout*** URL the item should point to, for example: _/mymodule/mywidget_ .
iconCls This is an optional attribute, the name of a CSS class goes here that should be defined in ***main.css***. It allows you add custom look. An example could be: _mytoolclass_ .

See? It's easy. You may add any number of shortcuts this way.

# The Background Editor

This tool allows you to set the background image a color of your desktop theme. You may use one of the nice images shipped with AppFlower or may upload your own pictures as well.

***To set the background image*** click one of the images in the list.

***To set the background color*** user color picker at the bottom. This will only be used if the image cannot be loaded for some reason.

***To upload a new image*** use the file upload control. You should upload JPG images only.

