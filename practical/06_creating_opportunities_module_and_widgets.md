# Creating the Opportunities Model and Widgets

The next part of our CRM application is all about sales! This will be a tool for tracking the business opportunities. It will allow us to manage our deals and will show us how our sales people perform, keeping us informed about the company's overall sales performance. 
 
## Creating the Opportunity Model

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/deals_model.png" rel="prettyPhoto" title=""><img alt="The Opportunity Model" src="/uploads/book/praticalcrm/deals_model.png" hspace="5" vspace="5"></a></div>

As always (until now at least) we'll begin with the Model creation. To accomplish managing opportunities, we want to assign a name, a description and an estimated worth to each deal. The creator of the opportunity and a contact person (on client's behalf) will be assigned as persons-in-charge and an expected close date will be also added. Knowing this date, we can try to predict the cash flow within the company. Each opportunity will therefore be linked (with relations) to a contact person (assigned_to), an employee who created it (created_by) and the client (account_id) it's related to. Translating this into the vocabulary of AppFlower Models, we end up with:



<pre>
id					(integer)	(unique identifier)
name				(varchar)
amount    			(integer)
account_id			(integer) 	(relation to account model)
assigned_to    		(integer) 	(relation to contact model)
description    		(longvarchar)
expected_closedate	(timestamp)
created_by			(integer)	(relation to afGuardUser model)
created_at			(timestamp)
</pre>
 
1. ***Creating the model*** Open up the Model pane, add a new Model and name it ***Opportunity***, then apply the above settings using the Model Editor. There is almost nothing new here: this is a model with field types you already know from previous chapters. We see that this model contains 3 relations and a new datatype of ***timestamp***. This represents _dates and times_ and is stored in a very portable, convertible way.

As for the relations, the following configuration should be used:
***account_id*** associates an opportunity with an account, so it should point to _Account -> id_. 
***assigned_to*** links a contact person to the deal, so it should point to _Contact -> id_.
 ***created_by*** field represents our employee, a person having access to the system, therefore it should point to _afGuardUser -> id_.

NOTICE:  If you're in doubt or need help, check out the following chapters to refresh your memory -:) <a href="/doc/1_1/practical_accounts_model">Creating the Account Model</a> about configuring models and for relations
 <a href="/doc/1_1/practical_contacts">Creating the Contact Model and Widgets</a>


## Building the Opportunity Widgets

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/deals_list.png" rel="prettyPhoto" title=""><img alt="The Opportunity List Widget" src="/uploads/book/praticalcrm/deals_list.png" hspace="5" vspace="5"></a></div>

2. ***Creating the Widgets*** You should create an Edit and a List widget  the way you did earlier (name them ***listDeals*** and ***editDeal***), and place them in ***opportunity*** module. This time they should be based on the Opportunity model.

NOTICE: Should you need a little help, have quick look at the chapters about <a href="/doc/1_1/practical_accounts_list">Creating the Account List</a> and <a href="/doc/1_1/practical_accounts_edit">Creating the Account Editor</a>

# Extending the Opportunity Widgets
When we've built the Account List we looked shortly into a few ways to make the List appear more elegant. Now we'll make some further adjustments, using the ***Widget Inspector***.

Let's open up the ***listDeals*** widget.

## Adding List Actions 
So far so good. The list is nice, page-able, sortable and we can run searches too. However, something is still missing: some buttons pointing to important tasks could really come in handy. For instance, we could have a button in the list that allows us to create a new record, and we need to be able to update records as well. To create these kind of controls, we need actions

3. ***Adding Create Action*** Right click the very first item in inspector and choose Add -> i:actions. A new component, called ***i:actions*** appears in the tree. Now, right click this and select Add -> i:action. The i:action child is being added. Finally, click this ***i:action*** element and edit some of its properties: set _name_ to ***new client***, _url_ to ***/opportunity/editDeal*** and _iconCls_ to ***icon-plus***.

If you've done everything right, a small button appears above the list. This is a link that points to an edit widget, which will allow us to update records or create new ones. You may add any number of such actions to a list, pointing to various important tasks.

Hit Save now, then preview your widget!

4. ***Adding Update Action*** As the last step, we're gonna add the update action too.  To do this, again, right click the very first item in inspector, but this time choose Add -> i:rowactions. Then, right click the newly added ***i:rowactions*** component and select Add -> i:action. Finally, edit the following properties of the new ***i:action*** element:

Set _name_ to ***edit***, _url_ to ***/opportunity/editDeal*** and _iconCls_ to ***icon-edit***.

5. ***Save and Preview*** Now hit Save and launch a preview! As you can see, a nice little icon appeared in the last column of your list. This is also a link, it points to the edit widget we mentioned above, which now allows you to update the corresponding entry. Such links always carry the id of the given record, so you may add other similar actions too, that operate on a particular record.
