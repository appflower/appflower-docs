# Managing Users in Studio
With Studio, your development environment is secured automatically, since it comes with a built-in authentication system. This allows you to add any number of users with different access levels. Only these authorized users will be able to access Studio and make changes to your application.

# The user manager
Click Studio Beta menu -> Users to start the user manager.

<div class="image_medium" style="float:right;"><a href="/uploads/book/user/user_management.png" rel="prettyPhoto" title=""><img alt="Managing Users in Studio" src="/uploads/book/user/user_management.png" hspace="5" vspace="5"></a></div>

A list of current users appears. The list shows some important details about each user and allows you to edit or remove any of them. For now it contains only one entry: the default user, having administrative rights.

# Adding a new user


<div class="image_medium" style="float:right;"><a href="/uploads/book/user/user_settings.png" rel="prettyPhoto" title=""><img alt="User Settings" src="/uploads/book/user/user_settings.png" hspace="5" vspace="5"></a></div> 

Click Create user button. 



This opens the user account editor. Fill in the details. Most of them are pretty straightforward (check the image on the right), only three of the fields require some explanation:

The password should be a secure one: _at least 8 characters long, should contain at least 2 numbers, 2 capital letters and a special character_ (like asterisk, punctuation symbol etc.).

The email address must be ***valid***, otherwise the user won't be able to reset his password later.

The role determines what rights the user has. Currently, there are two access levels: 
   - An ***Administrator*** has full access. He can change anything.
   - A ***Studio user*** can make changes to the application, but he cannot perform administrative tasks, such as _adding, removing or editing_ user accounts.

Click Save user data to add the new user.

# Editing users

Locate the user account you want to modify in the list and click the ***pencil icon***. This loads the user account editor. This time the form already contains the user's details (password is not shown for security reasons). A few remarks:

Administrators can change other users' passwords. However, please keep in mind that the user won't be notified about this automatically! You have to let them know "manually".
    
You may leave the password field blank in edit mode. This means you don't wish to change the password. If you are changing your own password, you'll be logged out automatically, and will have to sign in again.
    
Make your changes, then click Save user data button to apply them.

# Removing users
Locate the user account you wish to delete in the list, then click the ***red circle icon***.
    
NOTICE: : Attention! Deleting a user removes it ***permanently*** from the database. ***This action cannot be undone!***