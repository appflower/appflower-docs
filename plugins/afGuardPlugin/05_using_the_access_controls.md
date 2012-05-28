# Using the Access Controls
The security layer is now in place, but it's really not used yet. To make use of it, we have to apply the access controls objects (permissions) we have set earlier. Luckily, this is very easy and can be done right from Studio.

1. ***Edit security.yml*** Open one of your edit widgets using the Widget Designer. Click to the security.yml tab. The current security configuration is pretty simple: empty, so the widget has no access controls assigned yet. You can change this in many ways, lets start by looking at this example where we will enable the security layer and set credentials (access controls) for the edit view: 

<pre>
edit:
  credentials: accounts_edit
</pre>

Note that you've just used the name of a access control here (_accounts_edit_). The above means, the module is secured and the Edit widget should be accessible only by people with the ***accounts_edit*** privilege assigned. Users without this permission will instead see an "insufficient credentials" message when trying to access the widget. The only exception is the administrator user, who has the right to see and use anything.

The ***security.yml*** holds security settings of all the widgets in the given module. The general form of the security syntax look like this:

<pre>
some_widget:
  credentials: some_credentials

other_widget:
  credentials: other_credentials
</pre>

It is also possible to combine individual credentials and create more complex permissions. For example:

<pre>
list:
  credentials: [[accounts_list,other_permission]]
</pre>

In this case, the List widget will be accessible for users with ***either accounts_list or other_permission*** right. For everyone else, access will be denied. Another useful scenario could be:

<pre>
list:
  credentials: [accounts_list,other_permission]
</pre>

This is even more restrictive: only those users will be granted access, having ***both accounts_list and other_permission*** credentials.

2. ***Clearing the Cache*** Before you can use the permissions you need to apply them in the database (like explained in the previous chapter) and to the widgets. Then when you have defined a set of access control permissions you want to use you just apply them to the corresponding widgets. Once you've configured all widgets, go to Studio Console and run the following to clear the cache and force new settings to be loaded:

<pre>
sf cc
</pre>

NOTICE: Please keep in mind, that changes in security settings of widgets will take effect only upon next logon! If the user is already logged in, he has to sign out and sign in again!
