# Creating the Song Model
<div class="image_medium" style="float:right;"><a href="/uploads/book/model/01_models.png" rel="prettyPhoto" title=""><img alt="Model Navigator" src="/uploads/book/model/01_models.png" hspace="5" vspace="5"></a></div> 

In this chapter we will learn how to build our ***Music model*** using AppFlower.
You will see, it's not too complicated to do this. Let us start by opening up AppFlower Studio. For now, you don't have to load a project, the default one (playground) will do just fine. 

# 1. Creating a Model

Maybe you already noticed the Model pane located on the left. This is where all models are listed. Click the Add Model button, located at the bottom of the list. 

A new entry appears, whose name is the default _"NewModel"_ right now. Change it to ***Song*** then press enter. 

That's it. Our model, called ***Song*** is just being generated.  At this point, it is a valid, but not fully functional model. We need to ***add its fields*** to make it useful. 



# 2. The Model Editor
<div class="image_medium" style="float:right;"><a href="/uploads/book/model/02_model_grid.png" rel="prettyPhoto" title=""><img alt="Model Editor" src="/uploads/book/model/02_model_grid.png" hspace="5" vspace="5"></a></div> 

In order to add or modify the fields of a model, you have to open it first.Double-click the ***Song model*** in the left pane. The Model Editor appears, which has two tabs:

The Song tab is a _data browser_, it lists the already stored records. Obviously, it is empty at the moment, since we haven't added any songs to our database yet.

The Model Config tab displays a detailed _overview of the fields_ associated with a model. This is where you actually design your model by adding, removing or modifying fields and adjusting their settings. 

Click the Model Config tab now.

NOTICE: : Please ***save your changes regularly*** while working with the tools described below! The changes you make won't be stored automatically, without saving ***you can lose them***!

# 3. Designing Model Structure

<div class="image_medium" style="float:right;"><a href="/uploads/book/model/03_model_config.png" rel="prettyPhoto" title=""><img alt="Model Config" src="/uploads/book/model/03_model_config.png" hspace="5" vspace="5"></a></div> 

Now you should see a table structure with several columns. It looks like this, because AppFlower system sees the fields of a model in a bit different way than you do.: For you, these are just names. The system, however needs to know _some details about them_ in order to handle them properly. Most of those columns may seem to be a bit mysterious to you, but you don't have to worry: ***we need only the first two*** for now. 

These are enough to create simple applications, like our music catalog, an address book and more. The rest are used by advanced applications only, and they are throughly explained in the <a href="http://www.appflower.com/doc/1_1/devbook" >Developer Book</a>. For now, however, let us concentrate on the two columns we really need:


## ***Field Name*** 


The Name column is the ***name of the field*** you are about to create. It's just a word, could be anything that makes sense. Remember? We have defined the following fields for our Song model in the previous chapter:

<pre>
 title
 author
 genre
 location
</pre>	

So let's use them now! Click to the _Name_ column in the ***first row*** and type _"title"_.


## ***Field Type***

The Type column determines ***what kind of information*** a "title" is.  It is necessary to define this, because "information" is just an umbrella term: a word, a sentence, a full paragraph, a number, a date or the current time all represent information, but they have different purposes, so to say, _they are different types_.

The Model is well aware of this, thus it treats each of these in a slightly different way.  It does this to provide the best results for you and to make the storage mechanism _fast and efficient_. However, the Model cannot find out what sort of information a "title" should be on its own, you have to help by selecting the proper type.: Let's click the _Type_ column in the ***first row***.

A list of choices opens. But what the heck is this? Those "types" look weird, don't they? No worries. The following simple guide will help you understand the types in 10 seconds. This guide is not only for our example model, but you can use it with _any future model too_.

## ***A Quick Guide to Types***

Should the following statement fit the field you're creating, the type should be:


 - varchar : If it's a name of a person or a product, a word, a sentence or a phrase no longer than 255 letters
 - varchar : If it's an address, email, phone, fax or cell number
 - longvarchar : If it's a longer piece of text, like a paragraph
 - booelan : If it's an answer to a yes or no kind of question
 - integer : If it's a number without fractional part
 - float : If it's a number with fractional part
 - decimal : If it's anything related to money or an other numeric value that has to be very precise
 - timestamp : If it's a date or time


Which one to choose? Well, we can assume that the _title_ of a song will always consist of a few words, so ***varchar*** is the right choice. Simple, isn't? Of course there are many other types, but for most applications the above will be sufficient. If you wanna learn more about the rest, check out the <a href="http://www.appflower.com/doc/1_1/devbook" >Developer Book</a>.

<div class="image_medium" style="float:right;"><a href="/uploads/book/model/04_model_config_with_fields.png" rel="prettyPhoto" title=""><img alt="Adding Fields to Model" src="/uploads/book/model/04_model_config_with_fields.png" hspace="5" vspace="5"></a></div> 


## ***Adding the rest of the fields***

It's time to add the other fields to our model. To do that, simply repeat the two steps below for each field: Click anywhere in the ***last row***. A selection appears. Now click to Insert -> Insert after. This creates a new row, room for the next field. ***Name your field*** and ***choose a type for it*** as we described above.

Just like "title", the _"author", "genre" and "location"_ can be also described by a few words, so the ***varchar*** type will work with those as well.

<div class="image_medium" style="float:right;"><a href="/uploads/book/model/05_model_config_with_field_id.png" rel="prettyPhoto" title=""><img alt="Adding Id Field to Model" src="/uploads/book/model/05_model_config_with_field_id.png" hspace="5" vspace="5"></a></div>

## ***The ID field***

You are almost done! There is only one more thing to do.: you have to add a new field called _"id"_ to your model.  Click to the ***first row***, then click Insert -> Insert before. This inserts a new row before "title". 

Name this new entry "id" and ***make all the other settings blank***.

This is a special field which you will use not only with this, but with each and every model you create. The id is like an _automatic counter_. Whenever you store a new piece of information (a song in this case), the counter will be increased by one, thus the new entry _gets numbered_. For now, you don't have to dive into the details of this, just keep in mind that ***this is an important, unique identifier*** used by the system, and it will be useful to you as well later.

NOTICE: : For the sake of this tutorial, we created "id" as the last field, but normally ***this should be the first one you add***. No matter what information you wanna store or how your model looks like, it should have "id" as its first field.

<div class="image_medium" style="float:right;"><a href="/uploads/book/model/06_model_grid_entering_data.png" rel="prettyPhoto" title=""><img alt="Adding Data to Model" src="/uploads/book/model/06_model_grid_entering_data.png" hspace="5" vspace="5"></a></div> 

# 4. Adding Data to Your Model

Congratulations! You've just created your first model. Now it is ready to store your data, so why don't you try to add some records? 

Click to the ***Song*** tab to start adding your songs. As you can see, the data browser now has all those fields you defined before. It is a table structure and the fields are shown as columns. It's very easy to fill this table with data, just follow the steps below:

Click to the "'title" column. Key in a song title, then press the ***tab*** key. The cursor jumps to next column. Keep repeating this until all the columns are filled. Pressing tab in the last column will insert a new row automatically.

NOTICE: : ***Always leave the "id" field blank!*** It will be automatically filled in by the system when you push the save button.

You should take a break now. Have a coffee and some snacks, check your favorite blog. 

Back already? Eager to learn? How about some practice then?

# A Little Exercise

What you know so far is enough to create simple models. Why don't you try to build a model for something else? For instance, _a list of your contacts_, all the people you know. 


This will be a new model called ***People***. Try to think about what characteristics it should have, what information you want to store about your contacts? You can always check your cellphone for hints, it surely has a similar application. This is a good exercise. It's somewhat similar to the music catalog, yet it's different. Try to create it, and add some entries to it.
