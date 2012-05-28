# Methods of Deployment

AppFlower applications can be deployed in two ways.: manually, using an ***archived package*** or automatically, using ***rsync***. You may choose any of these methods, their results are exactly the same and both have their advantages.: The first method is easier to follow, therefore it is perhaps better for novice users, while using rsync has some extra benefits, but it is slightly more complicated too, thus it's probably more suitable for advanced users. 

You should choose the one that better fits your needs and and is easier for you to work with.


## The Easy Way: Using an Archive

Open up Studio and load the project you wish to deploy.

Click Project -> Export.

In a few moments, the system will create a <u>compressed file</u> for you and a download dialogue appears. This file contains all parts of your project,
_excluding those needed only for development_ and the temporary data (e.g.: cache).

Upload this file to the target host and unpack it in your web directory or decompress it on your computer and upload all its contents.

That's it. Your project should be now available on the target host. This method is usually better if you have limited access to the server, so for example in case of shared hosting accounts.

Your project is now deployed, but it's ***not operational yet***! There are a few simple settings to adjust, please read next chapter on finalizing the deployment.


## The Automatic Way: Using Rsync

It is also possible to upload your project to the production server directly from our virtual machine or other development environment, provided that the target can accept _SSH_ connections and the _rsync_ utility is installed on the source host. Like I said, while this method might require a bit more effort to configure, it has some cool benefits:

- An rsync connection has to be set up only once, and after that it allows you to deploy all future versions via a single command.
- Unlike FTP, with Rsync it is possible to transfer a project from one server to another directly.
- Since it works over an encrypted channel (SSH), it is more secure.

Open up Studio, load your project, then click Project -> Export DB. This will create database dump for you, and will prepare the project for upload.

If you've never deployed a project to the given production server from this development environment, ***establish an SSH connection now***. You can quickly connect, then disconnect. This allows you to add the target host to the list of known hosts, preventing future problems.

In the config folder of your project, there is a file called properties.ini. It has the following general structure:

<pre>
[production]
  host=www.yourproductionserver.com
  port=sshport
  user=sshuser
  dir=/your/web/directory
</pre>

You should simply update this file with the details of your production server. Let's see what setting are available here:

host: This is the domain name or IP address of your production server.

port: It is the port number of the SSH service. It should be 22, unless your hosting provider have changed it. If the default value doesn't work, contact their technical 
support. They should be able to tell you the right value.

user: A valid username goes here which you can use to establish SSH connections.

dir: This should be an absolute path to the web root directory on the production server. In case of shared hosting accounts, this the directory you see after logging in via FTP.

Once you finished editing the file, enter the project directory via the shell. Using our virtual machine, this can be done by issuing the following command:

<pre>
cd /var/www/yourproject 
</pre>

Once you're there, execute the command below:

<pre>
./symfony project:deploy production -t --go
</pre>

The transfer of your application will begin immediately, progress information will be shown on screen.

NOTICE: : Please be patient! It will take some time to perform this task, since a project contains a lot of data.

Your project is now deployed, bit it's ***not operational yet***! There are a few simple settings to adjust, please read on.
