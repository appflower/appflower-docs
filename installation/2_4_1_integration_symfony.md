# Integrating AF with Existing Applications

In this chapter we'll explain how to add AppFlower system to your existing or newly created Symfony 1.4 project. This can be done in two ways: using either Studio or the Engine package. These include only the AppFlower source code, without any examples, thus they are suitable for integrating AppFlower into your existing application. If you would like to set up a brand new SF / AF project or need examples, check out the <a href="/doc/1_1/learn_gitexamples" >Learning and Creating New Projects</a> chapter instead.

<p class="warning">This guide assumes that you are somebody with remarkable development experience are familiar with the Symfony framework. It also assumes that your ***Symfony 1.4*** project already exists and is configured properly: it is database-driven, and you can access it in a browser. Your project must also use the Propel ORM layer for database handling, as ***Doctrine is not supported*** yet!

So let's get started!

 1. Enter your project directory using the shell:

<pre>
cd /your_web_root_path/yourproject
</pre>

 2. Clone the appropriate GitHub repository. The command to be executed depends on which package you wish to install:

## For Studio..

<pre>
git clone git://github.com/appflower/appflower_studio.git ./plugins/appFlowerStudioPlugin
</pre>

You also need to fetch some required plug-ins:

<pre>
git clone git://github.com/appflower/appflower_engine.git ./plugins/appFlowerPlugin
git clone git://github.com/appflower/sfPropelSqlDiffPlugin.git ./plugins/sfPropelSqlDiffPlugin
git clone git://github.com/appflower/sfPropel15Plugin.git ./plugins/sfPropel15Plugin
git clone git://github.com/appflower/sfTaskExtraPlugin.git ./plugins/sfTaskExtraPlugin
</pre>

## For Engine..

<pre>
git clone git://github.com/appflower/appflower_engine.git ./plugins/appFlowerPlugin
</pre>


3. Make sure your application's database connection as well as the Propel connection details are correctly set. If you don't know how to do this, see <a href="/doc/1_1/learn_gitexamples" >Learning and Creating New Projects</a> chapter for a detailed explanation.

4. Fix any permissions related problems:
<pre>
 ./symfony project:permission
</pre>

If you're installing Studio, also run this command:

<pre>
 ./symfony afs:fix-perms
</pre>


5. Build database handler classes:
<pre>
 ./symfony propel:build-model
</pre>

6. Create database structure:

<pre>
 ./symfony propel:insert-sql
</pre>


8. Edit your /your_web_root_path/yourproject/apps/yourapp/lib/myUser.class.php file, and replace its contents with the following:

<pre>
class myUser extends afGuardSecurityUser implements AppFlowerSecurityUser
{
 public function  getAppFlowerUser() {
        return $this->getGuardUser();
    }
}
</pre>


9. Finally, if your application is not accessible via a virtual host, you'll have to adjust your web server settings now. This shouldn't be the case, since the standard Symfony way is also a virtual host. Anyway, if you need guidance, please see <a href="/doc/1_1/learn_vhost" >Configuring Apache Virtual Hosts</a> chapter for step-by-step instructions.

That's about it. Now your project should support AppFlower.

If you've installed Studio, open up ***http://your_virtual_host/studio***. The welcome screen should appear in a few seconds. In the meantime, you can check out the <a href="/doc/1_1/learningappflower" >Learning AppFlower</a> book to learn the basics and how to work with Studio.

Should you have installed the Engine, you'll need to build a widget or layout to test. You can learn more about these basic concepts in the <a href="/doc/1_1/learn_widget" >Widgets</a> and <a href="/doc/1_1/learn_layout" >Layouts</a> chapters of the Learning AppFlower book. Once you're familiar with these, check out our tutorials for developers to get started. 

<strong><u><a href="/doc/1_2/learn_install_finalstep">CONTINUE TO LAST PART OF INSTALLATION &gt;</a></u></strong> 
