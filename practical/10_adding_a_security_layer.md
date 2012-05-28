# afGuard Security

We want our employees to access the CRM application, and assign tasks and accounts to each. For this we will be needing a new user model to differentiate users and contacts. Users are those whom are allowed to access the CRM application, whereas contacts are people in our address book. We are lucky that appFlower provides a plugin named ***afGuardPlugin*** with a full featured security mechanism for applications.

The ***afGuard*** plugin enables you to separate access with different privileges within the an application. And to require those accessing the application to authenticate before they can proceed. This makes it possible to protect content or areas of the application like "Administration" to only certain people. afGuard also comes with a set of widgets to create and manage multiple, password protected user accounts. The plugin can manage any number of custom user-defined credentials, allowing you to give or deny access to views inside your application, such as individual widgets, layouts or even whole modules of your application. 

We will be using the afGuardPlugin to implement security. Fortunately, it is available in all projects created by Studio, so we just have to configure it. In this chapter we'll explain how to do this.

# How does this work?

***Permissions:*** afGuard security is based on permissions. These are simply named objects. For example, if we want somebody to have access to our Account List widget, we can create a permission called "account_view", while the "account_edit" credential could give access to the Account Edit widget and so on. You can name these anyhow and you can add any number of such credentials. 

***Roles:*** The second step is to group these permissions, thus create roles. A role is merely a set of permissions. For example, a role could be called "Operator" or "Administrator", each having different permissions assigned.   Of course, you may create any number of roles and may assign as many permissions to them as you wish.

***Users:*** The third task is to add user accounts. These are the people having access to our application. Each of them has one or more roles, depending on what tasks they have to perform using the application. A user's role will automatically assign all those permission associated with the role to the user. When using the application, the user will only see those functionalities he has permissions for. 

***Applying it all:*** Finally, we have to secure the components of our application to hide them from unauthorized users. This can be done right from Studio very easily. You can assign a custom set of permissions to any widget, layout or function (actions, buttons etc). Only users having the right permissions will be able to access the given resource. afGuard supports both simple permission lists as well as permission combos, allowing you to create even complex access control rules.

Well, that's enough theory! -:) Let's secure our CRM application to see all this in action!

# Adjusting security configuration

Open up Studio, then click to Layouts. Currently there is nothing interesting here, but not for long.

Go to Studio Console and perform the following command.: (the "cd .." is for Studio Console only, to do the copy from the root of your project)

<pre>
cd .. ; cp plugins/afGuardPlugin/config/pages/security.xml apps/frontend/config/pages
</pre>

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/security1.png" rel="prettyPhoto" title=""><img alt="Security Dashboard" src="/uploads/book/praticalcrm/security1.png" hspace="5" vspace="5"></a></div>

Now refresh the Layouts pane, the ***security.xml*** entry appears. Right click this and select Set Page as Homepage, then hit the
Run button to launch the application. In a few moments, the ***Security Dashboard*** shows up (pictured), this is where you adjust all the security settings.



<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/security2.png" rel="prettyPhoto" title=""><img alt="Adding a Permission" src="/uploads/book/praticalcrm/security2.png" hspace="5" vspace="5"></a></div>

Let's begin with adding some permissions. Click the Permissions tab, then hit New Permission. Simply name the permission ***admin***, add any description you like, then save it. If you refresh the permission list now (click the small button at the bottom), the new credential appears. You can add more permissions in the same way. For instance, you could create an access right for each of your widgets and layouts, a possible scenario can be found below. Note that you can also edit an existing permission by clicking its name, or delete it by hitting the small red icon on the right. Deleting multiple permissions is also possible. Just select multiple rows in the list (click the checkboxes) then choose More Actions -> Delete Selected or Delete All (to erase all records).



<pre>
accounts_view	(allows users to access accounts list)
accounts_edit	(allows users to edit accounts or create new ones)
contacts_view
contacts_edit
opportunity_view
opportunity_edit
activity_view
activity_edit
dashboard_view	(allows users to see the dashboard)
</pre>
 
<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/security4.png" rel="prettyPhoto" title=""><img alt="Adding a Role" src="/uploads/book/praticalcrm/security4.png" hspace="5" vspace="5"></a></div>

Let's continue with adding a role. Click the Users tab, then press New Role to do this. The Role editor appears, which should look something like the picture on the right. Here you can name the new role, add a description and assign permissions to it. Let's create a role called ***administrator*** and assign all permissions (or only the admin one) to it, since it will be a superuser. You can do this by dragging the permissions from the left box to the right one. Note you can select multiple entries by pressing SHIFT+Click and move them together. When you're done, hit Submit. Refresh the list of roles to see the new role appearing. You can edit or delete roles the same way as permissions..



<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/security5.png" rel="prettyPhoto" title=""><img alt="Adding a User" src="/uploads/book/praticalcrm/security5.png" hspace="5" vspace="5"></a></div>

Finally, it's time to create the admin user too. Click Add User to open the User editor. Type in ***admin*** as username and something else as  ***password*** (you'll be able to change this later). You also have to assign one or more roles to the new user, pretty much the same way you assigned permissions. Since it's the admin account, let's assign the ***admin*** role to it, then save the form. Refresh the list and the new user appears. As you can see, his status is active, even if you haven't checked that checkbox in the editor. The reason for this is new users are created with active status by default.



<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/security8.png" rel="prettyPhoto" title=""><img alt="Signing In" src="/uploads/book/praticalcrm/security8.png" hspace="5" vspace="5"></a></div>

Now that we have our first user with some credentials assigned, it's time to activate the security layer. Punch the Toggle Security button. In a few seconds, a message appears informing you about the operation was successful. Click the link to continue and you should end up at the login screen. From now on, you'll always have to login when working with the application (pushed Run in Studio or just opened it in the browser). You can sign in with admin username and the password you specified.  You may turn off security anytime, by clicking Toggle Security again, the permissions and settings will be preserved.



# Securing widgets

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/security7.png" rel="prettyPhoto" title=""><img alt="Securing a Widget" src="/uploads/book/praticalcrm/security7.png" hspace="5" vspace="5"></a></div>

Now our application is secure, but once a user has logged it, he can see and use all the widgets, since we haven't secured them yet. Let's see how to do this and secure the Account List widget.



Open Widgets pane in Studio and load ***accounts/listAccounts*** widget. When the Widget Designer shows up, click the security.yml tab.
A blank screen appears. Add the following content to it, then  press the Save button:

<pre>
listAccounts:
  credentials: [[admin, accounts_view]]
</pre>

This means, the list widget will be accessible for users with ***either accounts_view or admin*** rights. For everyone else, access will be denied.

Basically that's it. You may secure the other widgets this way too. There is a security.yml in each module of your application, and secured widgets stored in the given module must be listed in this file. So for example adding the accounts/editAccount widget to the above configuration would make it look like:

## Additional Options

<pre>
listAccounts:
  credentials: [[admin, accounts_view]]

editAccount:
  credentials: [[admin, accounts_edit]]
</pre> 

If you wish to make a widget accessible with only a certain permission, simply specify the name of that permission without [ ]:

<pre>
listAccounts:
  credentials: admin
</pre> 

If the widget requires multiple permissions, use this syntax instead:

<pre>
listAccounts:
  credentials: [some_credential, other_credential]
</pre> 

 Once you've configured all widgets, go to 
Studio Console and run the following to clear the cache and force new settings to be loaded:

<pre>
sf cc
</pre>

Of course there is more about security and there more settings to explore. But this should be enough for our CRM application. You can learn more about afGuard features in the <a href="/doc/1_1/afguardplugin">afGuard Plug-in documentation</a>.


