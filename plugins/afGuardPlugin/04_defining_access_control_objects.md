# Defining Access Controls Objects (permissions)
The next step for fully utilizing the afGuardPlugin is to define a set of access control objects which can be used and assigned to user roles. We will be using Fixtures to store database content, which can then be loaded each time the database gets rebuild. To ensure all deployments of the application has all permissions available.
 
1. ***Create Fixtures*** You want to create a new fixture file to store project permissions in ***permissions.yml*** and store this inside _data/fixtures_.

<pre>
mkdir data/fixtures
touch data/fixtures/permissions.yml
</pre>

2. ***Adding Permissions*** Then you need to fill out the permissions.yml file with a few entries. Each entry consists of a _name_ and a _description_. These don't have any technical aspects at this point, an entry merely specifies an access right and describes its purpose.

A sample content could look like this. And good way to divide access controls is to make it possible to group modules into edit and views. Then you can separate who can view and edit content belonging to that group of views. In this example we will use accounts as a group setting to all editing and viewing related to account views. You can also be more specific if needed.

<pre>
afGuardPermission:
  adminperm:
    name:           admin
    description:    Administrator permission
  accounts_view:
    name:           accounts_view
    description:    Allows user to see client list
  accounts_edit:
    name:           accounts_edit
    description:    Allows user to create or update clients
  dashboard_view:
    name:           dashboard_view
</pre>

WARNING: Before saving the file, make sure ***it doesn't contain any tabulator characters***, as those are illegal in YML. Indentation should be marked only by spaces!

3. ***Load Fixtures*** To have the permissions loaded in your database, you need to use the propel:data-load command.

<pre>
./symfony propel:data-load data/fixtures/permissions.yml
</pre>
