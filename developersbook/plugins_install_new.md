# Installing Plug-ins
Unfortunately, AppFlower doesn't provide an automated method for adding/removing plug-ins (yet!). But there is still some good news, since Symfony has such mechanisms. You can use these to install or uninstall any general purpose Symfony plug-in.  

If you don't know how to do this, please consult the <a href="http://www.symfony-project.org/gentle-introduction/1_4/en/17-Extending-Symfony#chapter_17_plug_ins">related part</a> of the Symfony documentation.

It is important to note however, that AppFlower specific plug-ins ***must be installed and uninstalled manually*** for now, since they are not available as PEAR packages. We will provide an easy to use installer in the near future, but until then you should follow the general method described here.

# Adding AppFlower Plug-ins

This is relatively simple, just follow the steps below:

1. Download the package from our website
2. Add the plug-in to the ./plugins folder of your application
3. See the README file (./README or ./docs/readme.txt) for further instructions.

You should always check the plug-in README file, since many plug-ins require some configuration changes or other customization to work properly.
 

The configuration files must be edited with a normal plain text editor! The most convenient solution is Studio's integrated editor, but you may also use applications like Notepad (Windows), TextEdit (Mac) or Emacs (Linux). Anyway, using something like MS Word is not recommended:-).

