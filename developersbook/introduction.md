# AppFlower Design
AppFlower applications use Symfony's PHP framework as their basis and server-side background. So, if you are familiar with Symfony, then using AppFlower should be pretty easy, since it simply extends this foundation. In fact, the AppFlower additions to Symfony are not really structural, but rather logical, or functional, in nature.

In other words, you can use the structure of Symfony that you already know so well with your AppFlower applications, too!

What is the difference, you ask?

Well, there are several differences. One is the configuration language we use. AppFlower configuration files are written in XML instead of YML. Also, the role of these files is more important, since they serve as the basis of AppFlower's logical units and functionality. A major part of your application's coding will be done in XML and only the advanced sections will require you to write PHP code, as well.

This XML language is a major part of AppFlower and is used to describe almost everything, from appearance to parameters and behavior. It's also a replacement for Symfony templates, as AppFlower doesn't use them.

To sum it up: an AppFlower application is simply an extended Symfony application that uses XML configuration files for every purpose, including the description of its views (which is why there are no templates or partials in AppFlower).

The basic logical unit (or individual entity) is called "View", or "Widget". A set of these Widgets is called a "Layout". You will find detailed descriptions of these terms in the next two sections, but for now it's enough to know that these are the building blocks of an AppFlower application.

Such a block consists of two parts:

An XML configuration that describes all aspects of the block (parameters, settings, behavior, appearance, etc.).

A Symfony action that can be used to call the Widget, or integrate it into a Layout. The Symfony internal URI serves as the Widget's unique id, as well.

The PHP code behind the Widget, or Layout, is partly provided by AppFlower "out-of-the-box" and for basic blocks, this is enough. Of course, more advanced use will require custom coding in the Action or Component levels. Libraries and ORM classes may also be used, but you don't have to worry. Feel free to use any of the Symfony tools as you would in a normal Symfony project. AppFlower is completely compatible with them (except those related to templates).

The configuration data of a Widget must be placed into the "config" directory of the Symfony module the Widget belongs to. The file must be named exactly after the corresponding action. For example: if you want to create a Widget called "Lister" in the "users" module, you would use this path:

<pre>
/$SF_DIR/apps/your_app/modules/users/config/lister.xml
</pre>

In regards to a Layout, the location of the configuration data is different, since a Layout always belongs to an application. Widgets, on the other hand, are related to a module.

For this reason, in order to create a Layout called "Lister", you'll have to use this path:

<pre>
$SF_DIR/apps/your_app/config/pages/lister.xml
</pre>

Please note that these file names are always case sensitive! The name of the file must be exactly the same as the name of the action, apart from the "execute" part. Thus, the following paths point to two different widgets:

<pre>
$SF_DIR/apps/your_app/config/pages/lister.xml
$SF_DIR/apps/your_app/config/pages/Lister.xml
</pre>