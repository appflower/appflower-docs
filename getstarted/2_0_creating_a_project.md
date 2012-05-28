# What is a Project?

A project is a kind of container, like a folder. It contains your AppFlower application and all other related things, such as documentation, images, licensing info etc. It also stores some extra info for Studio, which will be used to identify and load the project. 

Once a project has been created, you can open it with Studio anytime to edit its contents. You can make modifications to the application inside or the other data files it contains.

WARNING: Please note that the project creation feature described below is guaranteed to work ***with our Virtual Machine only***! If you're using a different environment, you might have to create the [database](../cookbook/database.md) and  [virtual host](http://www.appflower.com/doc/1_2/learn_vhost) manually. Please follow these links if you need help!

# How to create a Project?
It's easy you can just use your newly opened project. Or you can create a new project, if you want to have several projects by starting Studio and follow these steps (or using the installation process for git or the bundled package):

<div class="image_medium" style="float:right;"><a href="/uploads/book/projects/01_projectname.png" rel="prettyPhoto" title=""><img alt="Project Name" src="/uploads/book/projects/01_projectname.png" hspace="5" vspace="5"></a></div> 

Click to ***Studio Beta*** menu and select ***Project -> Create new project*** to start the wizard. 

1. Naming The first step is to name your project. Type in any name and press Next.


<div class="image_medium" style="float:right;"><a href="/uploads/book/projects/03_template_theme.png" rel="prettyPhoto" title=""><img alt="Theme Selection" src="/uploads/book/projects/03_template_theme.png" hspace="5" vspace="5"></a></div> 

2. Theme In this step you can select the look and feel of your application. Choose the theme you like and click Next.


<div class="image_medium" style="float:right;"><a href="/uploads/book/projects/04_new_user.png" rel="prettyPhoto" title=""><img alt="Creating a New User" src="/uploads/book/projects/04_new_user.png" hspace="5" vspace="5"></a></div> 

3. Developer user Now it's time to create a user account for Studio. This will be a developer user who is authorized to develop the appflower application, NOT a user of the application itself (you can add those as well, but later). The user can always change his password, so you may set any pass phrase here. For now, this single user is enough, you'll be able to add more once the project has been created. When you're finished, click Next to move on.

NOTICE: : Please note that the ***email address*** of the user should be a ***valid*** one, else changing the password later won't be possible.

<div class="image_medium" style="float:right;"><a href="/uploads/book/projects/06_virtualhost.PNG" rel="prettyPhoto" title=""><img alt="VirtualHost" src="/uploads/book/projects/06_virtualhost.PNG" hspace="5" vspace="5"></a></div> 

4. Server config We have arrived to the last step. Simply hit the Save project button to finish the wizard. 

AppFlower will now generate your project and will also modify the web server configuration, to make the project accessible via browser. This is a fully automated process, Studio will display a _notification dialog_ when it's done.

That's it! Congratulations, you have successfully created your first project! Once the wizard has finished its work, ***click the URL*** in notification dialog to load your project in a new browser window!

