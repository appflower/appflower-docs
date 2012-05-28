# Code Generator Options
Options to the Code Generator

## Options for fields section

***help***

This is the same as Symfony's options, but the AppFlower generator transforms this into an &lt;i:help&gt; element, whose rendering depends on the user's help settings.

***attributes***

This is not supported by AppFlower, but you can use the style attribute of the &lt;i:field&gt; element, which as the same purpose.

<pre>
fields:
  name: {label: Name, style: "width: 200px; color: blue" }
</pre>

***credentials***

The original purpose of this was to allow you to hide certain actions, or form fields, based on user credentials.

However, AppFlower doesn't support hiding form fields (yet); so, it implements this as a subsection of list (or form) and applies the given credentials to the corresponding view.

See form or list for details.

***renderer and renderer_arguments***

AF allows you to override the field's value using this declaration. The syntax is the following:

<pre>
fields:
  name: {label: Name, help: foo, renderer: { type: orm, class: Util, method: getFoo2, default: some }, renderer_arguments: {foo: 7, bar: 2} }
</pre>

As you can see, you can specify a class and a method of that class will be called to fetch the field's value. Arguments of the method can be passed via renderer_arguments.

***type***

AF expects a valid &lt;i:field&gt; input type.

***date_format***

This is supported, but instead of using the formatting parameters of PHP's date function, you must use ExtJS formatting options. Please see the following URL for details (click "Date"). <a href="http://dev.sencha.com/deploy/dev/docs/">http://dev.sencha.com/deploy/dev/docs/</a>

NOTICE: Please keep in mind that in addition to these options, you can use ALL AppFlower attributes in your field declarations!

## Options for list section

***batch_actions***

Actions listed under this subsection are transformed into &lt;i:moreactions&gt;.

***credentials***

As stated above, this is implemented as a subsection of list. If the user doesn't have the listed credentials, the List View won't be rendered. The syntax is the same as in Symfony's generator.

<pre>
list:
  credentials: [[ fofo, admin, defe ]]
</pre>

To hide an action (instead of setting credentials for the view), use the AppFlower condition attribute:

<pre>
actions:
  new: { label: Add new Stuff, url: "/lele/edit", iconCls: icon-plus, condition: "User:hasRights()" }
</pre>

***scripts***

This is an AppFlower addition. The JS files listed here are preloaded during parsing, so the code is available after rendering.

<pre>
list:
  scripts: [myscript,anotherfile]
</pre>

NOTICE: Please note: The files must be listed without the JS extension!

The following options are not supported by the AppFlower generator. This is either because AppFlower doesn't have the necessary API to implement them yet, or it is simply incompatible with them:

<pre>
Option
layout
params
pager_class
peer_method
peer_count_method
table_method
table_count_method
Options for form section
</pre>

***class***

It's not supported yet.

***title***

The title text of the Edit / Create / Show View.

***display***

It's the same as in Symfony's generator, with the exception of a few minor differences.

Since AppFlower suppots tabbed forms, you can make your form use tabs by placing a plus (+) sign before the fieldset title.

If you want to render the fields with floating enabled, add the minus (-) prefix to the fieldname in the field list:

<pre>
display:
  "+Set1": [title,-type_id,user_id,-owner_id,details]
  "+Set2": [hours_estimated,is_public]  
</pre>

The above example creates a tabbed view. The fieldset "Set1" will contain 5 fields, 2 in each row (except for the last one).

***scripts***

It's the same as in the list section.

***values***

This is another AppFlower addition. It is a subsection that allows you to override the value of a field, or specify a default value.

The default value is only used in "create mode" (when the Widget is called without the "id=" part); otherwise, the method of the class you refer to is called.

<pre>
values:
  due_at: { type: orm, class: Util, method: getFoo2, default: "1978-01-31 00:00:00" }
</pre>

It's possible to define the value as "static". In this case, the form field is always rendered using this value, regardless of mode (edit or create). The value is constant and cannot be changed later.

<pre>
values:
  due_at: { static: foo }
</pre>

***handlers***

This is another AppFlower addition. It is a subsection that allows you to attach JS event handlers to form fields. The syntax is straightforward and the declaration is transformed into &lt;i:handler&gt; elements.

The "type" should be a valid AppFlower event handler. The "action" contains the JS code to be executed when the event occurs.

<pre>
handlers:
  name: [ { type: blur, action: alert(1)} ]
</pre>

You may define multiple handlers for a form field, but they must have different types.

***validators***

This is also available only in AppFlower. You can specify a set of validators here, which will be used to validate the corresponding form field.

The declaration is transformed into a number of &lt;i:validator&gt; elements.

You can specify which validator you want to use with the "name" key and pass arguments to it using the "params" key.

<pre>
validators:
  name: [ { name: immValidatorRequired, params: {foo: bar, bar: 1} } ]
</pre>

You may define multiple validators for a form field.