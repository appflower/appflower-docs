# Desktop Theme

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/theme3.png" rel="prettyPhoto" title=""><img alt="Desktop shortcuts and startmenu links in action!" src="/uploads/book/praticalcrm/theme3.png" hspace="5" vspace="5"></a></div>

Now that we have a fully working app, let's make it a bit more smooth and glue the interface together. We already prepared a Dashboard layout, and a few working widgets. But we currently don't have any shortcuts on the Desktop to the widgets, nor in the menu. So let's add these.




<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/shortcutedit.PNG" rel="prettyPhoto" title=""><img alt="The desktop links editor" src="/uploads/book/praticalcrm/shortcutedit.PNG" hspace="5" vspace="5"></a></div>

1. ***Desktop Shortcuts*** on the Desktop we would like to place an icon for the Dashboard layout and all the Edit widgets. Click Theme Designer and a small popup will open. Since we already selected the Desktop Theme when we created the project, let's jump directly to the next tab named Editors and pick the ***Shortcuts Editor***. 

As you can see, the first shortcut (a link to the dashboard) has been already added by AppFlower. To add the editAccount desktop shortcut, right click to Shortcuts -> Add link on the right. A new entry appears in editor.  Now we should fill in its properties:

Set ***name*** to _item1_, ***title*** to _Edit Account_, ***url*** to _/accounts/editAccount_ and ***iconCls*** to _icon-plus_, then hit the Save button to save your changes.

You may add the remaining links in a similar manner using the following URL values:

<pre class="code">
Contacts (item2) -> /contacts/editContact
Opportunities (item3) -> /opportunity/editDeal
Activities (item4) -> /activity/editActivity
</pre>

That's it. If you save again, and launch the application using the ***Run*** button, you should see something like the screenshot above.

All the shortcuts will be rendered with simple icons. You can add new icons in Editors -> CSS Editor, by editing ***main.css*** file and adding some new CSS classes. 

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/menueditor.PNG" rel="prettyPhoto" title=""><img alt="The start menu editor" src="/uploads/book/praticalcrm/menueditor.PNG" hspace="5" vspace="5"></a></div>

2. ***Adding Menu Shortcuts*** we can also add shortcuts to the menu found when click the ***Start button***. Here we would like to add all the list widgets as well. Click Theme Designer, select ***Editors*** and now the Start Menu Editor. 

The editor is very similar to the previous one. Just like in that case, Dashboard has been added automatically. To add the next listAccounts menu item, right click to Menu -> Add -> item, then fill the properties as follows:

Set ***name*** to _item1_, ***label*** to _List Accounts_, ***url*** to _/accounts/listAccounts_ and ***icon*** to _/images/famfamfam/accept.png_, then hit the Save button to save your changes.

Now you should add the rest of the list widgets. The URLs and item names can be found below:

<pre class="code">
Contacts (item2) -> /contacts/listContacts
Opportunities (item3) -> /opportunity/listDeals
Activities (item4) -> /activity/listActivities
</pre>

Again, all these shortcuts will displayed using a default icon. You can change that by specifying another file. You can find hundreds of neat icons to choose from in ***/your_web_root/crm/web/images/famfamfam***

NOTICE: You can learn more about these editors in the Learning AppFlower chapter <a href="/doc/1_1/learn_theme">5. Customizing Appearance</a>.

