# Code Editor
<div class="image_medium" style="float:right;"><a href="/uploads/book/codeeditor/code_editor.png" rel="prettyPhoto" title=""><img alt="Code Editor" src="/uploads/book/codeeditor/code_editor.png" hspace="5" vspace="5"></a></div> 	


Studio has an integrated Code Editor based on <a href="http://ace.ajax.org/">ACE</a>, which can be used when writing business logic, editing configuration files or just about any other file in the project. And we want outline some of the gems for the editor in this chapter.

You may start up the Code Editor either by opening the side panel on the right when working with Widget Designer, or directly, by choosing Tools -> Code Browser.

## Features

The Code Editor comes with a bunch of features; which really can ease your job while working with AppFlower.

Some of the major features in the code editor is:

 * Syntax highlighting
 * Auto indentation and outdent * 
 * Search and replace with regular expressions
 * Highlight matching parentheses
 * Toggle between soft tabs and real tabs
 * Displays hidden characters
 * Highlight selected word



## The context menu

<div class="image_medium" style="float:right;"><a href="/uploads/book/codeeditor/1_1context.png" rel="prettyPhoto" title=""><img alt="Editor Context Menu" src="/uploads/book/codeeditor/1_1context.png" hspace="5" vspace="5"></a></div> 	

Right clicking any file or directory in the Code Editor will bring up a context menu with several useful tools. Let us describe each of these briefly below:

***Open*** lets you open a file. The editor supports basically any type of text file, and has syntax highlighting for PHP, YAML, XML and more.

***Reload*** refreshes the given folder or sub-folder (recursively).

***Expand all / Collapse all*** will expand or collapse the given directory recursively, so including all sub-folders. 

***Rename*** allows you rename a file or directory.

***Delete*** removes a given entry ***permanently***!

***New folder*** creates a new directory.

***New file*** adds a new, empty file with the specified extension.

<h5>_Uploading and Unpacking files_</h5>

***Upload file*** allows you to transfer ***one or more files*** from your computer to the server. 

Click Add and browse the file to be uploaded. You may select multiple files, just hit Add again and again. If you've changed your mind, press the small icon on the right to remove that item or the ***red X*** button to clear the list.

Once you've added all files, hit the Upload button. The transfer begins instantly, the files will be uploaded one after another. This may take a while to finish though if you've chosen bigger files.

***Unarchive*** will unpack compressed files to same directory where the archive resides. Currently ***zip and tar/gzip*** compressions are supported and therefore the file must have either _zip, tar.gz, or tgz_ extension to be recognized. 

## Keyboard shortcuts

Also of great value is the many <a href="https://github.com/ajaxorg/ace/wiki/Default-Keyboard-Shortcuts">Keyboard Shortcuts</a> which is worth having a look at.