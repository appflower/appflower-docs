# Staying Up-to-date with Latest AppFlower
The AppFlower project is updated regularly when _new features_ has been added, and when _bugs_ and _security issues_ has been solved. It is therefore highly recommended to update to date with latest version of AppFlower, since they make AppFlower more stable, reliable and improve its performance in many ways. All updates are available free of charge.

AppFlower has two major components: the ***AppFlower Engine*** and the visual tool, ***AppFlower Studio***. The source code of these is hosted by 
<a href="http://www.github.com/" >GitHub</a> and can be managed via the <a href="http://git-scm.com/" >Git version control system</a>.


## How-to check Current Version
To check the commit revisions of AppFlower, you can use the following Git commands. Open up the Studio Console (or a shell) and execute the following commands.
<pre>
git log --oneline -1
</pre>

<pre>
89fc3ae Added another scripts for VM needs
</pre>

You can also check to see at which commit all the plugins are:

<pre>
git submodule status --recursive
</pre>

Which in our case returned this output

<pre>
 31ddcee2a4e825509b150ae5714dce19800e06fa lib/vendor/symfony (heads/master)
 dca8f85a8a2431f3555c3a60761f9663191c9108 plugins/appFlowerPlugin (heads/master)
 6320dd75892e6698d7cb19dcfdf09df234e3aaa0 plugins/appFlowerStudioPlugin (heads/vm-image)
 d9af3f0908d9f30e26cf438afe487a54c1dada99 plugins/sfPropelSqlDiffPlugin (heads/master)
</pre>


# Updating AppFlower Source
Whether you've downloaded our virtual machine, or fetched the AF source code from our repositories, the git client should already be installed and configured correctly either on your computer or in the virtual machine. In order to fetch the newest updates, simply follow the steps below. Obviously, the first two are needed only if you're working with our 
vm.

1. Start up the virtual machine.

2. Log in to the console with username and password outlined in chapter 2.

3. Enter your project directory via shell. This can be done by executing the following command (assuming that you're using the vm).

<pre>
cd /var/www/yourproject
</pre>

4. Run the commands below to start the update process (in this order).

<pre>
git pull
git submodule update --init --recursive
</pre>

The Git client will now download and install all the updates _automatically_, normally it doesn't require any user intervention. It should take only a few minutes to patch up the whole AppFlower project. The above commands will update both Engine and Studio and they'll also freshen up all _installed AppFlower plug-ins_, provided they were added using Git.

If this fails, because your git client doesn't support the --recursive option. Then you should try without it, so it becomes.

<pre>
git pull
git submodule update --init
</pre>

NOTICE: : Please keep in mind that each new project contains a ***new instance*** of Studio and the Engine, so updates must be downloaded for
***each project, separately***!

5. Finally, you should clear the server cache, and regenerate widget cache, to make sure the system is using the updated files. To do this, run the 
following commands in ***Studio Console***:

<pre>
sf cc
appflower validator-cache frontend cache
</pre>

Basically, that's about it. You can test the changes in the browser now.

It should be noted, however, while we are doing our best to provide updates that can be installed automatically, on some rare occasions, 
this might just not be possible. Every once in a while, you'll have to adjust some settings or perform some simple tasks to make the changes take 
effect.
For this reason, you should always check our <a href="http://www.appflower.com" >web site</a> before updating the sources. It might be 
also a good idea to sign up to our RSS channel.