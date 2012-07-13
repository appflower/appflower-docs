# Routing and Links

When you are linking to widgets or layouts in your application, you should be using the format /#/module/action. So you need to make sure the module and action exist; 

Another option is to use routing, to have clean URLs, so if you add in routing.yml a new route like:

	my_profile:
  	url:   /user/myprofile
  	param: { module: afGuardUserProfile, action: edit }

then url could be called /#//user/myprofile instead of
 /#/afGuardUserProfile/edit