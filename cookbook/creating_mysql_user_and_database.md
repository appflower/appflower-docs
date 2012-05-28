# How to create a database and db user?

Open up the shell of your OS and launch the mysql client program, using the following command. If your root user doesn't have a password, you may omit the -p option.:



<pre>
mysql -u root -p
</pre>

Now type in the root password or just hit enter if your user doesn't have one. Then issue the following command:

<pre>
GRANT select,insert,update,delete,create,drop ON yourproject.* TO newuser@localhost IDENTIFIED BY 'password';
exit; 
</pre>

This will add a new user called "newuser" whose password will be "password".

NOTICE: It is considered ***good practice to provide a strong password***, which is at least 8 letters long, contains numbers, capital letters, and a punctuation symbol (e.g.  !StrongP@ssw0rd!,  DenmarK2100^,  AppF!0wer*). Using such a complex password is good for security reasons as it provides better protection for your database and the information stored in it. 