# What are Widgets?

Widgets are the ***building blocks*** of all AppFlower applications. They are small components, that perform certain tasks.: 

A widget can ***list*** the records stored in the database, can provide everything you need to ***modify or create*** those records, or may ***show*** you the details of a single record. Widgets are also able to display custom ***HTML*** content, like _messages, images or Graphs._ You can think of them as small, standalone programs.

Let's see a practical example, this will help us better understand the nature of widgets:

Suppose you want to build an application to manage the sales information of your company. ***
In this case you need a widget that lists your products, another one that allows you to edit product information or create new products, a third one that displays product details and so on. Probably you'll create several other widgets too, to deal with stuff like vendors, customers, orders, etc.

These widgets are the building blocks, and together they build up the product management application.

## Features of Widgets

Widgets (in general) have several useful features to make building powerful applications fast, easy and fun:

Powerful engine backgroundAll AppFlower Widgets come with a bunch of nice abilities that will work ***without any coding*** or configuration. For example: 

An Edit Widget does not only provide the input fields you need, it also comes with things like _advanced form validation_ and _rendering features_. Similarly, a List Widget is not only a static list of data, but it is interactive and thus allows that data to be _sorted, exported, has paging and search features_ and much more.

Each widget type has its own unique features.

Fully standalone behavior Widgets are ***independent of their environment***. This means, once you've created the Product List widget, you can _move it around your application_. For instance, you may place it into a certain layout, relocate it to another one later, or even display it in many different layouts at the same time. It will ***work anywhere***, out-of-the-box. No additional configuration is required!  


This gives you (and your users) a greater level of freedom and development flexibility. It also makes much easier to _reuse a widget in another application!_.

Power logic Widgets may have their own, ***custom business logic (PHP code)***, which allows them to perform very complex operations. This means, they can fetch the data form your database, manipulate it in various ways and _display custom results_

## Widget Types

Each widget is identified by a unique internal URI, which looks like this:
 
module_name/widget_name

AppFlower currently supports these kind of widgets:

List Lists records in various ways.
Edit Modifies or creates records.
Show Displays all details of a record. It's read-only, the record cannot be changed.
HTML Displays custom HTML content


