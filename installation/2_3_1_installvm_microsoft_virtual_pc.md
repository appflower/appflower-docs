# Installing AppFlower with Microsoft Virtual PC

WARNING: Supported versions: MS Virtual PC 2007 1.0 or newer or Windows Virtual PC. 

If you're running Windows 7 or Vista, you can use either the newest <a href="http://www.microsoft.com/windows/virtual-pc/download.aspx" 
>Windows Virtual PC</a>, or the older <a href="http://www.microsoft.com/download/en/details.aspx?id=4580" >Microsoft Virtual PC 2007</a> to run AppFlower, although the former is recommended. Users of older Windows versions (such as XP) should download Virtual PC 2007. Both packages can be obtained freely from Microsoft's website.

NOTICE: : ***A note for Windows 7 / Vista users:*** only Windows Virtual PC is needed to work with AF, so you ***don't have to download*** the XP 
compatibility bundle. Also keep in mind that once you've installed Windows Virtual PC, you won't be able to run VPC 2007 or any other older version anymore.

# Converting the AppFlower image

If you haven't done it already, fetch the <a href="http://cdn.appflower.com/vmware.zip">AppFlower package</a> now. Once you got it, unzip this file anywhere on your computer. It contains a single item called AppFlower.vmdk

In order to use the VMDK image with Virtual PC, you have to convert it to Microsoft's VHD format. This can be done in a number of ways. For example via a free 
utility, <a href="http://vmtoolkit.com/files/folders/converters/entry8.aspx" >VMDK to VHD Converter</a>, which is available at VMToolkit.com. It's very easy to use:

***1.*** Just download and unzip this file somewhere, then run Vmdk2Vhd.exe to start the utility.

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vmdk.PNG" rel="prettyPhoto" title=""><img alt="Converting VMDK to VHD" src="/uploads/book/virtualmachine/vmdk.PNG" hspace="5" vspace="5"></a></div> 

***2.*** Choose the AppFlower.vmdk file as ***Source Vmdk***.

***3.*** Type in C:\somefolder\AppFlower.vhd as ***Destination Vhd***.

***4.*** Finally, hit Convert to create the VHD file. This will take a few minutes, please be patient.



# Setting up Windows Virtual PC VM

Start up Virtual PC via Start Menu -> Windows Virtual PC. Click Create new virtual machine at the top. A wizard opens, which should be completed as follows:

***Step 1:*** Type in AppFlower as ***Name*** and C:\myvm as ***Location***. 
The program will create this directory for you.

***Step 2:*** Add 512MB of ***RAM*** and make sure the networking checkbox is checked.

***Step 3:*** Use the Existing virtual hard disk option and browse the VHD file you've just created with the converter program.

That should be it. Now the wizard closes and you can run Start Menu -> Windows Virtual PC again. A list of virtual 
machines appears with only one entry. Double click the AppFlower VM to start it. AppFlower should boot up in a short while.

# Setting up MS Virtual PC 2007 VM

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_1.PNG" rel="prettyPhoto" title=""><img alt="Virtual PC list" src="/uploads/book/virtualmachine/vpc2007_1.PNG" hspace="5" vspace="5"></a></div> 

Start up Virtual PC then click New to create a new VM. A wizard shows up:



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_2.PNG" rel="prettyPhoto" title=""><img alt="Create new virtual machine" src="/uploads/book/virtualmachine/vpc2007_2.PNG" hspace="5" vspace="5"></a></div> 

***Step 1:*** Click ***Next***, select Create new virtual machine, then hit Next again.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_3.PNG" rel="prettyPhoto" title=""><img alt="Location of VM" src="/uploads/book/virtualmachine/vpc2007_3.PNG" hspace="5" vspace="5"></a></div> 

***Step 2:*** Type in a location for the new VM (for example C:\myvm\AppFlower.vmc), then hit ***Next*** to continue.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_4.PNG" rel="prettyPhoto" title=""><img alt="Configuration overview" src="/uploads/book/virtualmachine/vpc2007_4.PNG" hspace="5" vspace="5"></a></div> 

***Step 3:*** Virtual PC now display a default configuration. Leave everything as is, then press ***Next***.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_5.PNG" rel="prettyPhoto" title=""><img alt="Memory options" src="/uploads/book/virtualmachine/vpc2007_5.PNG" hspace="5" vspace="5"></a></div> 

***Step 4:*** Select the Adjusting the RAM option and set it to ***512MB*** using the slider.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_6.PNG" rel="prettyPhoto" title=""><img alt="Hard disk options" src="/uploads/book/virtualmachine/vpc2007_6.PNG" hspace="5" vspace="5"></a></div> 

***Step 5:*** Choose the An existing virtual hard disk option and press ***Next***.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/vpc2007_7.PNG" rel="prettyPhoto" title=""><img alt="Hard disk location" src="/uploads/book/virtualmachine/vpc2007_7.PNG" hspace="5" vspace="5"></a></div> 

***Step 6:*** Finally, browse the VHD file you've created earlier, push ***Next***, then press ***Finish*** to close the wizard.



The new virtual machine now appears in the list of VMs, you can start it by clicking the Start button. AppFlower 
should boot up in a few seconds.

<strong><u><a href="/doc/1_2/learn_install_finalstep">CONTINUE TO LAST PART OF INSTALLATION &gt;</a></u></strong> 

