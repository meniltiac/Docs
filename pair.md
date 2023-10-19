#Pair 

##Copying a site
### Wordpress 

####Files 

1. In Pair admin, set up new domain name for development site
2. Get access to the Pair account.
3. SSH to the server using the Pair credentials (`ssh username@username.pairserver.com`)
4. zip contents of live site (`zip -r nameOfZipFile folderToZip`)
5. Move nameOfZipFile to new development site folder
6. `unzip nameOfZipFile`
7. The files are now likely one level too deep. To move up a level, use `mv nameOfZipFile/* .`
8. You must now change the contents of the `wp-config.php` file, based on a new database.

####Databases
1. In Pair admin, navigate to "Manage Your Databases"
2. Go into the production database (if you do not know which one is attached to the production site, you can see it by accessing the server and looking in the 'wp-config.php' file for the production site.
3. Using PhPMyAdmin, log into the production database and click on 'export'
4. export a .sql file of the entire database
5. Close the production database
6. In Pair admin, create a new database
7. When the screen that includes the db username/password shows up, copy the read/write username and password into the `wp-config.php` file for your development site
8. Save all the database credentials to a safe place
9. Log into the new DB using PhPMyAdmin
10. Import the .sql file from the production DB into the new DB
11. In the `wp-options` table, change the urls to use the new domain. So for instance if the live domain was https://abc.com and the dev domain is http://dev.abc.com make sure that everything is changed over to the latter domain name.

The development site should now be installed. 
