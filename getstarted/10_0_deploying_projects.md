# Deploying AppFlower Applications

<div class="image_medium" style="float:right;"><a href="/uploads/book/deploy/export.png" rel="prettyPhoto" title=""><img alt="Export Project for Deployment" src="/uploads/book/deploy/thumb/export.png" hspace="5" vspace="5"></a></div> 

Software created with Studio is easy to deploy. The built-in project export tool will automatically create a compressed package with all the necessary files included, which you can obtain via a single click. All you have to do is to unpack this package on the target host, and make some adjustments to bring your project to life.

It is also possible to deploy a project _automatically_, over the network or to transfer it from one server to another directly.

This chapter will provide all necessary information about the components you need to make AppFlower running and it will also throughly explain how to deploy a project created with Studio. Provided that certain perquisites are available, AppFlower applications will work on almost any modern OS.

By default there is enabled debugging setting for production environment. Before deployment it is highly recommended to disable debugging in production environment.
This can be achieved by uncommenting
//$configuration = ProjectConfiguration::getApplicationConfiguration('frontend', 'prod', false);
and commenting
$configuration = ProjectConfiguration::getApplicationConfiguration('frontend', 'dev', true);
line in web/index.php file.
