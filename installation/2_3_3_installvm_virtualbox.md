# Installing AppFlower with VirtualBox
Download and install <a href="http://www.virtualbox.org/wiki/Downloads">VirtualBox</a>. You need to grab one of the files listed under ***VirtualBox binaries***. Linux, MacOS and Windows versions are available.

<p class="warning">Supported versions: Oracle VirtualBox 4.1 or higher. 

Below you can find a quick video tutorial showing you how to install AppFlower with VirtualBox. All the instructions are also outlined below.

<iframe src="http://player.vimeo.com/video/21965153" width="500" height="281" frameborder="0"></iframe>

# Installation instructions for Windows
Get the file VirtualBox for Windows hosts x86/amd64 (_find link in the top_). Once it has been downloaded, run it. An installation Wizard opens. You don't need to change any of the settings, just click ***Next*** or ***Yes*** every time, then in the last step click ***Install***. Now VirtualBox installation begins. Please be patient, it may take a while to finish.

NOTE: While the software is installing you might be presented with several questions or warnings. Click ***Yes*** each time.

When installation is completed, click to ***Finish***. This will start up VirtualBox right away.

# Installation instructions for MacOSX
Get the file VirtualBox for OSX hosts x86/amd64 (_find link in the top_). Load it up then double-click the first option. This will start the installer. You don't need to tweak any settings, just install it to your local hard drive.

Once installation is done, close the Installer. Now you should be able to find VirtualBox among your ***Applications***. Please start up VirtualBox now to continue.

# Starting the Virtual Machine
<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/1_vm_name_and_os.png" rel="prettyPhoto" title=""><img alt="VirtualBox: Name and OS" src="/uploads/book/virtualmachine/1_vm_name_and_os.png" hspace="5" vspace="5"></a></div> 

 1. Once VirtualBox is running, click ***New***. This will start the new new virtual machine wizard. Type in a name for the new virtual machine (e.g.: appflower). ***Operating System*** must be Linux, and ***Version*** should be set to Other Linux. Then click ***Next***.

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/2_vm_memory.png" rel="prettyPhoto" title=""><img alt="VirtualBox: Memory" src="/uploads/book/virtualmachine/2_vm_memory.png" hspace="5" vspace="5"></a></div> 

 2. We suggest to set the memory of the Virtual Machine to 512MB. Click ***Next***.

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/3_vm_disksize.png" rel="prettyPhoto" title=""><img alt="VirtualBox: Disk space" src="/uploads/book/virtualmachine/3_vm_disksize.png" hspace="5" vspace="5"></a></div> 

 3. Select the virtual hard disk you wish to use. This is the appflower.vmdk file you downloaded from our website and decompressed. Select Boot hard disk option. Click Use existing hard disk, then browse to the appflower.vmdk file. Click ***Next***. That's it, press ***Finish*** to close the Wizard.

<div style="clear:both;"></div>
<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/4_vm_storage.png" rel="prettyPhoto" title=""><img alt="VirtualBox: Storage" src="/uploads/book/virtualmachine/4_vm_storage.png" hspace="5" vspace="5"></a></div> 

 4. Now right click the newly created virtual machine, then click ***Settings***. You need to check two things here.: Click ***Storage***, and check if the appflower.vmdk file was added under the IDE controller. Click ***Network***, and make sure it is set to Bridged Adapter.


NOTE: Depending on the network settings of your computer, the "Bridged" opttion might fail. In that case, choose ***NAT*** instead.

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/5_vm_network.png" rel="prettyPhoto" title=""><img alt="VirtualBox: Network" src="/uploads/book/virtualmachine/5_vm_network.png" hspace="5" vspace="5"></a></div> 

<div style="clear:both;"></div>

 5. If you are running Windows, click ***System*** and make sure Enable IO APIC is checked. Otherwise you can skip this step.

<div class="image_medium" style="float:right;"><a href="/uploads/book/virtualmachine/7_vm_system.png" rel="prettyPhoto" title=""><img alt="VirtualBox: System" src="/uploads/book/virtualmachine/7_vm_system.png" hspace="5" vspace="5"></a></div> 

<div style="clear:both;"></div>

 6. The installation process is now finished! You can startup your AppFlower virtual machine by double clicking it. In a few seconds, the AppFlower system shows up.

<strong><u><a href="/doc/1_2/learn_install_finalstep">CONTINUE TO LAST PART OF INSTALLATION &gt;</a></u></strong> 
