---
layout: post
title: "FroSoCo Technology Stack"
description: ""
category: tutorial
tagline: "Web Programming in PHP and CodeIgniter"
tags: [intermediate, web, php, codeigniter, datamapper]
---
{% include JB/setup %}

## PART 1: Setting Up
###Application Installation (Compatible with Mac/ Windows/ Linux)
* [XAMPP Server 5.6.15](https://www.apachefriends.org/index.html) -- Cross platform local PHP/ Apache server with MySQL
* [Sublime Text 2](http://www.sublimetext.com/2) -- Cross platform development environment (to edit our code!)

###Technology Stack Overview
The starred links have tutorials worth reviewing for basic knowledge. Because the FroSoCo website combines a lot of these technologies, it is important to understand that the database portions in the CodeIgniter tutorial do things differently than we will be learning in this tutorial.
* [PHP 5.4.44](http://php.net/manual/en/index.php) -- Server scripting language.
* [CodeIgniter 2.1.4](https://codeigniter.com/user_guide/)* -- Model-View-Controller web framework built on PHP
* [DataMapper ORM](http://datamapper.wanwizard.eu/pages/toc.html)* -- Easier database models
* [MySQL](http://dev.mysql.com/doc/refman/5.7/en/) -- The underlying database that stores our data
* [CodeIgniter Template Library](https://github.com/jenssegers/CodeIgniter-Template-Library) -- Template engine to make our designs consistent


###Install, Open, and Configure XAMPP
Right after successful installation, choose the option to open the XAMPP control panel before quitting the installer. Here's how you can open the XAMPP Control Panel in the future.

* Mac: Applications folder > XAMPP > manager-osx (Path: "/Applications/XAMPP/manager-osx")

* Windows: Start > Programs > XAMPP


1. Open the XAMPP Control Panel.

2. Click "Manage Servers" tab on the top bar in the XAMPP Control Panel.

3. Click the name that says "Apache Web Server" in the main panel. Then, once this row is highlighted, hit the "Configure" button on the right.

4. Click "Open Conf File" in the pop-up and then hit "Yes" to proceed with editing the file.

5. Paste the following lines right after the line (around line 230) that says `<Directory "/Applications/XAMPP/xamppfiles/htdocs">` (for Windows it will be a little bit different file path):

			AllowOverride All
			Options +Indexes
			DirectoryIndex index.php
			Order allow,deny
			Allow from all

###Get Starter Code for FroSoCo Website
1. [Download starter code](https://github.com/frosoco/frosoco-starter/archive/master.zip).

2. Extract the downloaded .zip file anywhere, but remember where you extract it to.

3. Click "Open Application Folder" in the "Welcome" tab of the XAMPP Control Panel (You will need to have started the control panel as indicated in the previous section).

4. Find and open the "htdocs" folder in this directory.

5. Delete all the contents of the "htdocs" folder.

6. Copy all of the files and folders from inside the unzipped folder from step 2 to "htdocs".

###Set Up Database
1. [Download frosoco_db_import.sql file](/frosoco_db_import.sql).

2. Point your browser to localhost/phpmyadmin.

3. Hit "Databases" button on top bar.

4. Type in 'g_frosoco_frosoco' and hit "Create."

5. Hit "Import" on top bar.

6. Hit "Choose File" and open the frosoco_db_import.sql file you downloaded in Step 1.

At this point, you will have set up the local server to host your code on localhost, the starter code for this tutorial, and a database that will store the data that your code will be able to access & modify. To see the product of your hard work, click on the "Welcome" tab

##Part 2: Adding a Simple, Static Webpage
###Create a Static Application View

###Modify the "home.php" Controller to Display the View

##Part 3: Templating / Consistent Design

##Part 4: Creating a Dynamic Webpage

###Database Administration

###Create a Database Model in Application Code

###Create a Dynamic Application View

###Create a Controller to Link Data to the View