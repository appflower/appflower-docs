# Installing AppFlower with Parallels Desktop

WARNING: Supported versions: Parallels Desktop 4.0 or newer. 

AppFlower runs smoothly under <a href="http://www.parallels.com" >Parallels Desktop</a> too, although installation requires a little tweaking for technical reasons. In order to install AppFlower, you have to convert it to Parallels' native HDD format first. Luckily this is very easy to do and doesn't require any 
external tools, since the converter is already available in your application.

If you haven't done it already, fetch the <a href="http://cdn.appflower.com/vmware.zip">AppFlower package</a> now. Once you got it, unzip this file anywhere on your computer. It contains a single item called AppFlower.vmdk

# Running Paralells Transporter

Select File -> Run Parallels Transporter to begin. The importer wizard opens, which should be completed as 
follows:

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/transporter1.png" rel="prettyPhoto" title=""><img alt="Migration Mode" src="/uploads/book/virtualmachine/transporter1.png" hspace="5" vspace="5"></a></div> 

***Step 1:*** Click ***Continue***, then select Express migration mode.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/transporter2.png" rel="prettyPhoto" title=""><img alt="Source Type" src="/uploads/book/virtualmachine/transporter2.png" hspace="5" vspace="5"></a></div> 

***Step 2:*** In the next step, choose Virtual Machine source type, then move on.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/transporter3.png" rel="prettyPhoto" title=""><img alt="Migration Object" src="/uploads/book/virtualmachine/transporter3.png" hspace="5" vspace="5"></a></div> 

***Step 3:*** Now you have to select the migration object which should be a Virtual disk. Move on to the next step.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/transporter4.png" rel="prettyPhoto" title=""><img alt="Virtual disk location" src="/uploads/book/virtualmachine/transporter4.png" hspace="5" vspace="5"></a></div> 

***Step 4:*** It's time to browse the VMDK file you've just unzipped. Select this file, then hit ***Migrate*** to start the conversion.



The Transporter will now convert your AppFlower.vmdk file to something Parallels Desktop can use. This will take several minutes, please be 
patient.

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/transporter5.png" rel="prettyPhoto" title=""><img alt="Hard disk role" src="/uploads/book/virtualmachine/transporter5.png" hspace="5" vspace="5"></a></div> 

***Step 5:*** Once the process has been finished, choose the Bootable option in the last step, and move on.



Parallels Desktop will complain about not being able to make the disk image bootable, but that's OK. You can safely ignore this warning. Before you finish the wizard, Parallels will show you where the converted HDD image is stored. Remember this location, you'll need it later.

# Setting up the Virtual Machine

It's time to create our virtual machine. Go to Parallels Desktop and select File -> New Virtual Machine. A wizard 
starts up that will guide you through the beauties of VM creation and setup -:). Let's see how it works:

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels1.png" rel="prettyPhoto" title=""><img alt="Operating system detection" src="/uploads/book/virtualmachine/parallels1.png" hspace="5" vspace="5"></a></div> 

***Step 1:*** The first step specifies a boot disk. Click the Skip Detection button at the bottom. We don't need OS detection, it is already installed.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels2.png" rel="prettyPhoto" title=""><img alt="Operating system" src="/uploads/book/virtualmachine/parallels2.png" hspace="5" vspace="5"></a></div> 

***Step 2:*** In the next step, select ***Linux*** as operating system and ***Other Linux*** as version, then move on.




<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels3.png" rel="prettyPhoto" title=""><img alt="Virtual machine type" src="/uploads/book/virtualmachine/parallels3.png" hspace="5" vspace="5"></a></div> 

***Step 3:*** Choose the Custom virtual machine type and click Continue.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels4.png" rel="prettyPhoto" title=""><img alt="CPU and memory" src="/uploads/book/virtualmachine/parallels4.png" hspace="5" vspace="5"></a></div> 

***Step 4:*** On the next screen you can adjust CPU and memory settings. Make sure RAM is at least ***512MB*** and leave the rest of the settings intact.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels5.png" rel="prettyPhoto" title=""><img alt="Hard disk options" src="/uploads/book/virtualmachine/parallels5.png" hspace="5" vspace="5"></a></div> 

***Step 5:*** Select the Existing image file hard disk option, then click Continue.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels6.png" rel="prettyPhoto" title=""><img alt="Hard disk file location" src="/uploads/book/virtualmachine/parallels6.png" hspace="5" vspace="5"></a></div> 

***Step 6:*** We have arrived to the step where you have to use the HDD file Transporter generated for you. Click Choose and 
browse the file (it should be called ***/Users/youruser/Documents/Parallels/AppFlower/AppFlower.hdd***), then move to the next step.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels7.png" rel="prettyPhoto" title=""><img alt="Networking" src="/uploads/book/virtualmachine/parallels7.png" hspace="5" vspace="5"></a></div>

***Step 7:*** Select Shared Networking to let the VM use your Mac's network configuration.




<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels9.png" rel="prettyPhoto" title=""><img alt="Optimization options" src="/uploads/book/virtualmachine/parallels9.png" hspace="5" vspace="5"></a></div>

***Step 8:*** The optimization options shouldn't be changed. Leave the selection on Virtual machine.



<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/parallels10.png" rel="prettyPhoto" title=""><img alt="VM Naming" src="/uploads/book/virtualmachine/parallels10.png" hspace="5" vspace="5"></a></div>

***Step 9:*** Finally, you have to name your new VM. Type in ***AppFlower***, then  hit the ***Create*** button to generate the VM.



In the last step, you don't have to change anything. You can start up the AppFlower VM by clicking Start now. It should boot up in a few moments.

<strong><u><a href="/doc/1_2/learn_install_finalstep">CONTINUE TO LAST PART OF INSTALLATION &gt;</a></u></strong> 
