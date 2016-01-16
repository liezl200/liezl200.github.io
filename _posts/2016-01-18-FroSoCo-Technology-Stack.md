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

##Ideas for Exploration

###Event Signups
- Have a general template: event title, location, time, blurb/description, money etc
- Allow the addition of individualized questions: do you have a car/how many does it seat, meal preferences/dietary restrictions, name of guest etc.
- Send automatic reminders: 3 days prior to the event (with a note asking them to let us know ASAP about cancelations) and the day-of the event
	- this could be via email and/or text
- Have a way to close the sign-up
- Have a randomizer in case there are more students who sign-up vs. spots available
- Keep a running tally of the wait list people in case there are cancellations
- Confirming reservation: if everyone can attend, then it will automatically confirm when they RSVP
- If it's a limited event (ie. 10 tickets), then after the sign-ups close, the event creator can go in and mark residents as "confirmed" or "wait listed" - it will then email them their status
the event creator should be able to change the status between "confirmed," "wait listed," and "cancelled" throughout the process as they get more information from students
keeping this list up-to-date helps track the process and gives us firm counts for the event, as well as noting the fluctuation/cancellations, and helps with financial accounting when we need to submit a list of who attended
- If there's a payment involved: be able to mark who has paid, hasn't
send them automatic reminders about paying
- A back-end database to archive and track this data longitudinally is helpful & can assist with a lot of the functionality ie. tracking who is/isn't coming to events, or what types of events get a large turn-out and which don't, or the types of events we're doing throughout the year (so we can try and have depth and breadth), or who cancels a lot and we may need to talk with about their RSVP/attendance
- A way for residents to create events as well so they can invite fellow dorm mates to athletic events or concerts they're playing in, or gather a group to go to the movies or visit an on-campus lecture together, or get folks together to practice a new language and/or have a music/jam session
this is a way to help the community become more self-authoring and self-sustaining
- A way that non-FroSoCo students can sign-up for events, ie. for screw-your-roommate, or if we want to allow our residents to invite 1 guest for something - this is a much lower priority and may not be used often

###Communication Challenges
- Figure out a way to re-connect events and FroSoCo information with a format that students are already checking often (so it's in their normal daily habits vs. something added), ie. with Facebook (FB)
- pre-FB the FroSoCo website was THE place where students could read each other's bios, see pics of events that were happening in the dorm, and find out about upcoming events - so they checked it a lot, and therefore were well-informed about what was happening in the dorm
post-FB, we haven't been able to figure out a way to tie these things together as well
- Maybe we could try and have daily/weekly questions or challenges, and that might draw people
but again, it's an added step vs. something that's already in their daily habits

###Photos & Videos
- Have a feature where we can either connect with FB photos that students are already uploading
- Or have a feature where residents can upload FroSoCo specific photos & videos; these need to be vetted in some fashion because the FroSoCo website has a broad audience - ie. we want "appropriate" photos
- Photos/videos help with promotional materials - brochures, handouts etc.
images for the website - which is a big attractor for new students, as well as something parents can check to see their child is doing well
- Archival purposes of the fun events and community we've built over the year
- Slideshows at banquets and special events, etc.

###Calendar
- Have a more visually-friendly way to see what's happening this week, and this month, on the website
- Our switch to Google calendars helps students synch with the FroSoCo calendar
maybe have instructions on the website about how to sign-up for the FroSoCo calendar
- Mainly we need a dedicated student staff member to update the planning and public calendars regularly and send out reminders - this has been a little shaky recently
- The calendar events should be linked with the event-signups
and maybe if someone RSVPs it sends them a calendar invite so it's on their personal calendars as well & the time is blocked off
- Have a way to feature/highlight especially important events, ie. Dean's events, big name speakers, etc. that we're trying to promote and have high-attendance
- Not sure if we want to do this, but it could be useful to have hall-specific sub-calendars so we can coordinate those events as well

###A back-end database with resident information
- this was helpful because it had all of the relevant resident information that we need at different times of the year
	- First name, last name, email, phone number, birthday, gender, SUID, Adams/Schiff, room number, frosh/soph/staff, dietary restrictions, ER contact information, a photo, etc.
- Then when we needed the info, we could concatenate it with the event sign-up vs. having to ask them to fill those questions out again

###Miscellaneous features we've had in the past
- SoSems: blurbs about the seminars, publicity, sign-ups, and email lists of the final class groupings
- Lounge reservation system - that the staff controlled, but that students could sign-up for
- Residential tutoring sessions that are in/around Governor's Corner - especially since we no longer have our own tutors
this could be a part of the calendaring function
- DAHA and DAWA message boards, to try and keep those requests off the chat list
a subset of this is usually buying/selling books at the end/beginning of each quarter
- Class lists/study session connectors - so people can find out who else is in Chem 33, create a study group and then message each other about study sessions in the lounge
a subset of this is "which classes do you recommend?" and/or "who are some great professors" - which could be an interesting list that gets added to each year
- Polls for things, ie. which professors to invite for Dean's Dinners
- SuperShuttle groupings - to get discounts when people are leaving for the holidays
- Thanksgiving hangouts - for those who are around during the holiday week

###Other Ways to Communicate
- Right now we generally have these mediums:
		* email
		* bathroom flyers
		* hall white boards
		* signs on the exit doors
		* hall and house announcements
		* Facebook
- There could be a ton of others: instagram, snap chat, vines, a youtube channel, etc.