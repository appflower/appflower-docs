# Managing Users
You would most likely want a way to manage your users. One way to do this, is to use the pre-build widgets available for afGuardPlugin and add these to a layout.

## Adding a Security Panel to Your Application
The easiest way to add afGuardPlugin controls to the UI of your application, is creating a Layout. This will be your security overview, accessible only by administrators. You'll see all your users, roles and credentials listed here.

1. Click to Layouts pane in Studio. Hit Add Page button to create a new layout. Name it ***users.xml*** and press enter.

2. The Layout Editor shows up. Our layout is empty at the moment, let's add some widgets to it! Click Add Widget button, located at the top of editor. A list of all your application and plug-in modules opens. Select ***afGuardPlugin -> afGuardUser -> list.xml*** and hit Add Widget at the bottom.

The widget's ***placeholder*** now appears in the layout. Do the same with ***afGuardPlugin -> afGuarGroup -> list.xml*** as well, then save the layout changes.

If you launch a preview in browser or run the layout, you'll see a screen with both the user and role listings. Now you can start managing your user accounts. This layout is currently accessible by anyone, so we should secure it asap. 
