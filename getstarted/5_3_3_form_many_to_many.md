# Relations 
Relations are used to connect content across models. 

## One-to-Many relations

Video: http://vimeo.com/channels/appflower/31474613

## Many-to-Many relations

A Many-to-Many relation is used when you want to assign multiple items to an item. Like a list of customers, where each customer can order many products. In this case you would like to assign multiple products.

### 1. Building the Model
1. Create a model named customer, with id and name field.
2. Create a model named product, with id and name.
3. Create a new model which relates the orders. Name the model order, and give it the fields id, customer_id (and relate it to customer.id) and product_id (and relate it to product.id). Let's create a last field to store the date of purchase, this field is date and type of date.

Now you have setup the models, for storing multiple orders each containing one product associated to a customer.

### 2. Building the Form widget
To have your form take usage of this new many-to-many relation you simply just build a new edit widget. And you will have to selection, where you can pick a customer and product for the order. An alternative design method is to use the  doublemulticombo field-type.

***basic form with many-to-many***:
1. Create new edit widget, select location to module customer. Widget name to makeOrders.
2. Select order and select the fields order.customer_id, order.product_id and order.date. 

Now save the widget and you have a working many-to-many relation.

Video: http://vimeo.com/channels/appflower/31474613

TIP: setup the customer and product model to have name selected as the toString. This will render values in the selection as names rather than ids.

***doublemulticombo field many-to-many***:
Let's say you already have an edit customer widget, and want to add the Orders doublemulticombo. In Widget Designer:

	- Add i:field to i:fields set name to orders and label Orders.
	- Change type for i:field orders to be doublemulticombo
	- Add i:value to i:field orders, and change structure to "class & method"
	- Add i:class to the new i:value, set _content to "ModelCriteriaFetcher"
	- Add new i:method to i:value, set name to "getDataForDoubleComboWidget"
	- Add param to the new i:method, and change name to "source_model", and _content to "Product"
	- Add new param to i:method, and change name to "glue_field_name", and _content "customer_id"
	- Add new param to i:method, and change name to "glue_field_value" and change _content to "{id}"
	- Add new param to i:method, and change name to "middle_model", and _content to "Order"
	- Add new param to i:method, and change name to "middle_model_field", and _content to product_id

Now since you are editing a customer, the doublemulticombo field only needs to show a selection of products. Where you can select multiple at once, and relate to that customer.

Video: http://vimeo.com/channels/appflower/31473799 see step 6.

See sample at:
 - http://samples.demo.appflower.com/#/forms/manyToMany
 - http://samples.demo.appflower.com/studio#widget#frontend/forms/manyToMany