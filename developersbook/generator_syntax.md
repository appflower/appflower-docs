# Code Generator YML syntax - Basic structure
Although AppFlower uses XML exclusively to describe configuration data, the generator is an exception; in this case, YML is used. The reason for this is the underlying Symfony Admin Generator, which is also YML-based.

The AppFlower task can read and parse the same generator.yml file as Symfony, but the syntax is not completely the same. AppFlower has specific options and subsections, while some Symfony options are not yet supported, due to incompatibilities with AppFlower.

The structure of the YML file expected by AF is as follows:

<pre>
generator:
  class: sfPropelGenerator
  param:
    model_class:           Ticket
    theme:                 appFlower
    non_verbose_templates: true
    with_show:             false
    singular:              Ticket
    plural:                Tickets
    route_prefix:          ~
    with_propel_route:     false
    actions_base_class:    sfActions
    default_actions: true
    pager:           true

    config:
      actions: ~
      fields:  ~
      list:
        title: 
        scripts:
        credentials:
        fields:
        display:
        hide:
        sort:
        max_per_page:
        batch_actions:
        object_actions:
        actions:
      filter:  ~
      form:
        title:
        scripts:
        credentials:
        fields:
        display:
        values:
        handlers:
        validators:
        actions:
      edit:    ~
      new:     ~
</prE>

As you can see, most of the global parameters are the same, we have only two new values and the "with_propel_route" is always false, due to the unsupported routing.

The two new params are:

***default_actions***
pager
default_actions

This is a boolean value, true by default. If it's enabled, the generator will add some actions automatically to the List and Edit / Show views:

***List View Actions***

Delete all
Delete selected

***Edit View Actions***
Add new item

These are automatically added and you cannot change their attributes later. If you wish to define these actions manually, set this option to "false".

***pager***

This is also a boolean value. When set to "true", the List View is pageable; otherwise, the paging controls are removed.

## Generator YML syntax - Config sections
As for the keys listed under "config" (the content part), you can use all subsections supported by the Symfony task, but not all of them will be used by AppFlower.

Why? Well, first of all, the AppFlower generator only uses the main ***fields, list, and form*** sections.

This is because the others are not compatible with AppFlower's design. We don't have a separate create/edit mode, so there is no need for the edit and new sections. The actions section is also unnecessary, because in AppFlower the Edit and List Views don't have any actions in common. The filters section is also ignored, because AppFlower provides this functionality out-of-the-box.

Regardless of these things, you can still use the keys. They will be recognized by the Symfony task and safely ignored by the AppFlower generator.

NOTICE: Please note: while you may use all the Symfony generator options in AppFlower's generator.yml, it won't work the other way around! The Symfony generator will only validate the YML content; it won't recognize the AppFlower-specific data!

***fields***

This should contain the global definition of the list columns and form fields (like in Symfony). Inheritance is supported, so you can redefine any of the fields (or columns) under either the list, or the form subsections. Those rules will override the global declarations.

It is also valid to redeclare only a part of the rule, in which case the generator will only update the original definition.

***list***

It should contain all List View specific declarations

***form***

The Edit / Show View specific definitons should be placed here.


## Generator YML syntax - Options
Options are the actual definitions allowed in the generator.yml file, located under "config" and its subsections.

AppFlower supports most options used by the Symfony task; incompatible options are safely ignored.

Aside from these, you can use any AppFlower attribute in field (or column) definitions.

We will list the AppFlower-specific options below, as well as those with different implementations in the AppFlower generator, or are simply not supported by AppFlower. The latter will be printed in red.

You can find the rest of the options in the Symfony documentation: <a href="http://www.symfony-project.org/reference/1_4/en/06-Admin-Generator">http://www.symfony-project.org/reference/1_4/en/06-Admin-Generator</a>.