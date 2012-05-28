# Creating the Activity Module and Widgets
We have arrived to the last functional part of our application: an activity module. Communication with customers and partners may happen in various different ways, such as phone calls, emails or by personal meetings. These events are always related to a certain topic, like a sales inquiry or an ongoing negotiation. Obviously, it would be useful to keep track of these somehow. So we can keep a client history record but also for scheduling new upcoming activities.

Furthermore, most of these events will require the involvement of several people to achieve the desired results. For example, think of a sales inquiry, which is probably answered by a sales representative, but a project manager or colleague might want to collaborate later on.

Well, the tool we're about to build will provide a solution for this. We'll be able to create and manage various events, each having a subject, a description, a deadline and people responsible for it. An event will have a status too, so different people can join the related discussion at different times, as progress requires it.


## Creating the Activity and Status Model

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/activity1.png" rel="prettyPhoto" title=""><img alt="Status Model" src="/uploads/book/praticalcrm/activity1.png" hspace="5" vspace="5"></a></div> 

1. ***Creating the Status Model*** Each activity will have a status assigned, and this status could change over time depending on the business workflow. So it's best to create a separate model to manage these statuses, for easy management later on. We just need an id as a unique identifier, a name for the status and an optional description. Open up Studio and create the Status model using the tools you've already learned so far.

<pre>
id
name	   (varchar)
description  (longvarchar)
</pre>

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/activity2.png" rel="prettyPhoto" title=""><img alt="Activity Model" src="/uploads/book/praticalcrm/activity2.png" hspace="5" vspace="5"></a></div>

2. ***Creating the Activity Model*** Now let's repeat the steps, and create the activity model where ***account_id, contact_id, status_id and created_by*** should be relations pointing to the ***id*** field of _Account, Contact, Status and afGuardUser_ models, respectively.

<pre>
id
subject		(varchar)
account_id	(integer)    (relation to account model)
contact_id	(integer)    (relation to contacts)
status_id	(integer)    (relation to status model (new))
created_by	(integer)    (relation to afGuardUser model)
description	(longvarchar)
due_at		(timestamp)
</pre>

NOTICE: If you got stuck, you can review the instructions about <a href="http://www.appflower.com/doc/1_1/practical_accounts_model">Creating the Accounts Model</a> and <a href="http://www.appflower.com/doc/1_1/practical_contacts">Creating the Contacts Model and Widgets</a> for details about relations

3. ***Adding Statuses*** Once you've got the models build, we should add a few entries to the status model like _planning, held and cancelled_. These describe the workflow of an activity: a scheduled activity is tagged (planning), and the outcome is either accomplished (held) or failed (cancelled). You can always extend this later. 

## Creating the Widgets

<div class="image_medium" style="float:right;"><a href="/uploads/book/praticalcrm/activity3.png" rel="prettyPhoto" title=""><img alt="Activity List Widget" src="/uploads/book/praticalcrm/activity3.png" hspace="5" vspace="5"></a></div>

4. ***Building the Widgets*** We want to build a List and Edit view for both the status and the activity model. So in total that should be 4 widgets we should be creating. You should already know how to accomplish this by now. Go on, click the Widget pane and add these new tools with the ***Create new Widget*** wizard. Add a ***listActivities*** and ***editActivity*** widget inside ***activity*** module, and an ***editStatus*** and ***listStatuses*** widget in ***status*** module.

<p class ="note">Should you get stuck, have a quick look at the chapters: 
<a href="http://www.appflower.com/doc/1_1/practical_accounts_list">Creating the Client List</a> and <a href="http://www.appflower.com/doc/1_1/practical_accounts_edit">Creating the Client Editor</a>


# Extending the Edit Activity Widget
In the previous chapters we looked at how we could extend our List widgets with more powerful actions. Now we will take a look on the Edit Widget, and see how we can add some useful features such as  comments, online widget help and form actions.

## Adding Field Comments and Tooltips  
The label of a field is usually a short keyword label which describes its purpose, but sometimes this is not enough. Some fields require a short explanation or a few tips on how to fill them. For this purpose, you can use the _i:help_ and the _i:tooltip_ elements:

5. ***Adding Field Comment*** Right click the ***subject*** field under ***i:fields*** and select Add -> i:help. Now click to the newly added element, then fill its __content_ property with some descriptive text, for instance: "a short self-explaining task oriented subject for the opportunity". This text will appear below the field. You can add such comment to all the other fields as well.

6. ***Adding Field Tooltip*** Again, right click the ***subject*** field under ***i:fields*** and select Add -> i:tooltip this time. Now click to the newly added element, then fill its __content_ property with some text, such as: "additional info on this opportunity". This text will appear whenever you move your mouse pointer over the form field. Such hovering messages could be used as helpful hints.

## Adding Form Actions
Just like Lists, Edit views may have actions too. These appear as ***buttons*** placed at the bottom of the form, and are useful for linking important widgets or to external resources. For example, our form could really use a back button, pointing to the list of activities, so you can jump to the list easily after editing a record.

7. ***Adding a Back Button*** Right click the very first item in the inspector tree and choose Add -> i:actions. Then right click the newly added element and select Add -> i:action. Finally, click this ***i:action*** element and edit some of its properties set: 


name to ***back to list***
url to ***/activity/listActivities***
iconCls to ***icon-back***


