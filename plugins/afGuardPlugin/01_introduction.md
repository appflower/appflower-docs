# afGuardPlugin: Access Control and Authentication
AppFlower provides a plugin with a full featured security layer for enterprise applications. The ***afGuard*** plugin enables your application to separated access privileges between users and to have your application require users to authenticate before they can proceed. This makes it possible to protect different areas of your application like "Administration" to only certain people with the right access. 

afGuard also comes with a set of widgets to create and manage multiple, password protected user accounts. The plug-in can manage any number of custom user-defined credentials, allowing you to give or deny access to views inside your application, such as individual widgets, layouts or even whole modules of your application.

NOTICE: Moreover, afGuard also offers a built-in authorization and session management mechanism, password reset feature and supports Chaptcha verifications (although this requires afChaptcha plug-in to be installed). It is based on the similarly named Symfony plug-in, _sfGuard_ and is it's an enhanced AppFlower counterpart.


## The afGuard Widgets
***screenshot of user creation***

The afGuard plug-in comes with a couple of cool widgets. These allow you to fully manage user accounts and the related data. You may run any of the widgets directly, like: ***http://your_virtual_host/#/module/widget***. Let's have a quick look at each of these tools:

afGuardGroup/list This widget lists _user roles_, like "operators" or "administrators". These could be also called groups. Each role is associated with one or more site permissions, that is, things the user can do, ("see this list" or "edit that content" etc). A user might have any number of roles but he must have at least one. This determines his access rights. The widget allows you to _browse_ existing roles. The ***Create*** button lets you add a new role, the small _pencil_ icon allows you to modify an existing item and you can remove any role by clicking its _red cross_ icon.

afGuardGroup/edit This is where you _create new roles_ or make modifications. Each role must have a name, a description and some site permission assigned to it.

afGuardUser/list The widget _lists user accounts_. It offers the same tasks as the list of roles: you can create, update, delete users or just browse the listing. The ***Add User*** button starts account creation. The ***Manage Roles*** button takes you to the role list.

afGuardUser/edit The form _creates new user accounts_ or modifies old ones. This is where you change or set all the user's details, including initial passwords (the user will be able to reset this later) and the user's role.  

afGuardAuth/signin This widget is the _login form_. The user signs in here. If you have afChaptcha plug-in installed, this widget displays a chaptcha verification after a certain amount of failed login attempts. Resetting forgotten passwords can be also started here.

afGuardAuth/logout This is not really a widget, but an action of afGuard. It logs out the user and terminates his session.
