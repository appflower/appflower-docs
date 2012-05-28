# Installing afGuardPlugin

The instructions for adding the plug-in to your project can be found below. Please note that in the near future we'll provide an installer mechanism for all our plug-ins, to make
installation really quick and easy. You should also keep in mind that the most up-to-date instructions will always be available in the plug-in's readme file, which is located in <span 
class="code_snippet">plugins/afGuardPlugin/README.

1. ***Open project folder***. Open up the shell and go to your project directory. This might be different on your environment.

<pre>
cd /www/yourproject
</pre>

2. ***Download Plugin*** Fetch the source code of the plug-in with the usage of git:

<pre>
git clone git@github.com:appflower/afGuardPlugin.git ./plugins/afGuardPlugin
</pre>

3. ***Build Model*** Now, you have to configure your project, so it can use the plug-in. This involves running some system commands as well as changing a few configuration files. First of all, run the following commands. These will update your database and generate the required models:


<pre>
./symfony propel:build-model
./symfony propel:build-sql
./symfony cc
./symfony propel:insert-sql
</pre>

4. ***Enable Security*** The next step is to open apps/frontend/config/security.yml and  apps/frontend/modules/pages/config/security.yml in an editor, and enable the security layer by changing the value of is_secure:

<pre>
  is_secure: true
</pre>

NOTICE: Using our virtual machine, the easy editor ***nano*** is already installed which can become very handy now and then. You can also use the Editor within Studio.

5. ***Get User Data*** Open and edit the configuration file config/ProjectConfiguration.class.php and add the following method to it. This tells the application how to get user data.

<pre>
 public function getAppFlowerUserQuery()
 {
    return new afGuardUserPeer();
 }
</pre>

6. ***Change to afGuardSecurityUser*** Open the file apps/frontend/lib/myUser.class.php to replace the default Symfony security solution with afGuard. Find and change the line below


<pre>
class myUser extends sfGuardSecurityUser

  // and change it to

class myUser extends afGuardSecurityUser implements AppFlowerSecurityUser
</pre>

7. ***Remember Me*** Finally, modify the file apps/frontend/config/filters.yml and add the security filter. This allows you to use the "remember me" functionality of the plug-in's sign-in page.

<pre>
security:
  class: afGuardBasicSecurityFilter
</pre>

NOTICE: If you are working with a project created with Studio, you're already done and you may skip the remaining steps. However, if you're using a "hand-made" project, you should read on! 

## Further steps for manual created projects

8. ***Activate afGuardPlugin*** Edit the apps/frontend/config/settings.yml file. You have to make quite a few changes here. First, locate the ***enabled_modules*** line under the 
section ***all***, and add _afGuardAuth, afGuardUser, afGuardGroup_ modules. This activates the user management widgets. And then, find the .actions part (also under section all) and specify the default action. So the changes should look something like.


<pre>
all:
  .actions:
    login_module:           afGuardAuth   # To be called when a non-authenticated user
    login_action:           signin        # Tries to access a secure page

   # ... in the .settings

  .settings:
    compat_10:              on
    enabled_modules: [default...afGuardAuth, afGuardUser, afGuardGroup]
</pre>

9. ***Copy Template*** And for last but not least copy the template ***layoutAuth.php*** from the plugin to your application template folder:

<pre>
cp plugins/afGuardPlugin/templates/layoutAuth.php apps/frontend/templates/
</pre>

That's it the plugin should now be ready to use. If you reload Studio you should see a number of new models (afGuard*) in the Model pane.
