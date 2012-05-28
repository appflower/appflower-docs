# Installing AppFlower with VMWare Fusion
Since the AppFlower package was created under VMWare, it supports both <a href="http://www.vmware.com/products/workstation/overview.html" 
>VMWare Workstation</a> and <a href="http://www.vmware.com/products/fusion/overview.html" >Fusion</a>. For Mac users, the latter is the only option since Workstation is not available for OS X.

NOTICE: : Please note that Fusion 4.x only works with MacOS X Lion or Snow Leopard, users of older OS X versions should download Fusion 3.x instead.

If you haven't done it already, fetch the <a href="http://cdn.appflower.com/vmware.zip">AppFlower package</a> now. Once you got it, unzip this file anywhere on your computer. It contains a single item called AppFlower.vmdk

# Setting the Virtual Machine

Launch VMWare Fusion and choose File -> New to create a new virtual machine.

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/fusion1.png" rel="prettyPhoto" title=""><img alt="New virtual machine" src="/uploads/book/virtualmachine/fusion1.png" hspace="5" vspace="5"></a></div> 

***Step 1:*** Just hit the Continue without disc button.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/fusion2.png" rel="prettyPhoto" title=""><img alt="Installation media" src="/uploads/book/virtualmachine/fusion2.png" hspace="5" vspace="5"></a></div> 

***Step 2:*** Select Use an existing virtual disk as installation media and browse the VMDK file you've just unzipped.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/fusion3.png" rel="prettyPhoto" title=""><img alt="Operating system" src="/uploads/book/virtualmachine/fusion3.png" hspace="5" vspace="5"></a></div> 

***Step 3:*** In the next step, choose Linux as operating system and Other Linux 2.6.x kernel 
as version.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/fusion4.png" rel="prettyPhoto" title=""><img alt="Customize settings" src="/uploads/book/virtualmachine/fusion4.png" hspace="5" vspace="5"></a></div> 

***Step 4:*** Finally, hit the Customize Settings button, then name your new VM ***AppFlower*** and press enter to close the wizard.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/fusion5.png" rel="prettyPhoto" title=""><img alt="RAM adjustment" src="/uploads/book/virtualmachine/fusion5.png" hspace="5" vspace="5"></a></div> 

***Step 5:*** The new virtual machine now gets created and the settings panel shows up. Click to Processor & RAM and adjust the 
amount of RAM to ***512MB***. Close the settings panel.



You might also want to check the Network setting and make sure it is either ***NAT*** or ***Bridged***, otherwise your new VM won't have access to the Internet.

That's it. Now you can start the new virtual machine by double clicking its screen in the Virtual Machine Library. AppFlower will boot up in a few moments. 

<strong><u><a href="/doc/1_2/learn_install_finalstep">CONTINUE TO LAST PART OF INSTALLATION &gt;</a></u></strong> 
