# Creating and Editing a plug-in using Studio
AppFlower Studio comes with a powerful code editor and a couple cool functions to make creation of plug-ins easy.: It automatically generates the necessary Symfony structure for you and puts everything to the right place.  Furthermore, it allows you to add modules and fully functional AppFlower widgets to your plug-ins!

This means, you can create mini AppFlower applications as plug-ins or turn parts of your big program into such things very fast and with ease. This will come in handy in many cases. And of course, the built-in code editor allows you to add complex logic to your plug-in widgets too, making your plug-ins really powerful.

Let's try this now, and create a test plug-in!

# Creating a Plug-in

<div class="image_medium" style="float:right;"><a href="/uploads/book/plugin/plugins.png" rel="prettyPhoto" title=""><img alt="Plugin Navigation" src="/uploads/book/plugin/plugins.png" hspace="5" vspace="5"></a></div> 

1. Start Well, let's get started, shall we? In the left pane of Studio, click to Plugins, then hit Add Plugin button at the bottom of the list. This will add a new entry to the plug-in list.

2. Plugin Naming To continue, you must change the temporary name of the plug-in. Type ***TestPlugin*** and press enter.

NOTICE: Please note that you may name a plug-in anyhow, but the name ***MUST*** end with the ***Plugin*** keyword.

3. Adding a Module Now that the new plug-in has been created, you should add a module and a widget to it, to make it useful. Right click to the plug-in name and select Add Module. The new module appears. 

NOTICE: This context menu has 3 options. ***Add Module*** puts a new module into the the plug-in, ***Rename Plugin*** allows you the change the name, while ***Delete Plugin*** removes the plug-in and all associated files permanently.You should keep in mind that deleting a plug-in is an irreversible operation! ***It cannot be undone!***
 
4. Changing Module Name The next step is to change the temporary name of the new module. 



Type ***Test*** as module name and hit enter.



 This will generate the module structure for you. Feels familiar? Yeah, you've done this before.. when you built your Music Library widgets.

5. Adding a Widget Finally, we have to add a widget to our module.


 Click Add Widget button (located at the bottom). 



A Wizard opens which again looks awfully familiar. No wonder, since this is the same wizard we used in the <a href="/doc/1_1/learn_widget">Widgets chapter</a> to build some cool Edit and List widgets. 
It works exactly the same way, the only difference is that the "Module Location" menu in step 1 shows only plug-in modules this time, your application modules are not listed.
Since you already know this wizard, it will be easy to fill in the details in Step 1 and to select the Model properties you need in Step 2.

Once you've completed the wizard, the Widget Designer opens up, which is another familiar tool. Here you can adjust your widget settings in the same way you did before.
So let's create a List widget called ***Test***. If you are in doubt, just follow the instructions of chapter 7.1, <a href="/doc/1_1/learn_widget_create" >Creating a List Widget</a>.

Well, basically that's it. Of course there is more about plug-ins, but the rest are advanced topics.

You may repeat the above steps to add as many widgets and modules to your plug-in as you need. These steps should be enough to create any kind of plug-in Studio can build for you.

# A Word on Editing Plug-ins

You may also use the plug-in pane to edit existing plug-ins. In the list you'll find not only the plug-in names, but also their modules and widgets. Modification works the same way as creation.: you can rename or remove plug-ins, add modules to them or delete existing modules, create new widgets..etc. These can be done as we described above and in the Widgets chapter.