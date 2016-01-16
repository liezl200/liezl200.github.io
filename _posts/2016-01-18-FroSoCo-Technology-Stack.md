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

##Part 2: Adding a Static Webpage

###Modify the "home.php" Controller to Display the View

1. Add the following code to the file "application/controllers/home.php" after the policies function (paste on line #213):

			/**
			 *
			 *
			 * URL: /home/preassignment
			 */
			public function preassignment()
			{
				$this->template->title = 'Preassignment';
				$this->template->content->view('static/preassignment');
				$this->template->publish();
			}

###Create a Static Application View

1. Create a new file and save it as "application/views/static/preassignment.php" (since we have already added the `preassignment()` function to the home.php controller, we should be able to point our browsers to the url 'localhost/home/preassignment' and be able to see a blank page). Feel free to periodically refresh the webpage as you are working on it so you can see how the page changes with each step or two.

2. We'll start building this webpage by adding a header for the page.

			<div class="page-header">
				<h1>Preassignment</h1>
			</div>

3. After this code, add a content section as follows. You can begin to notice patterns, namely that the `<div>` tags (HTML tags are anything with < > and follow special syntax rules to produce text exactly how you want it to look) denote particular sections and that the different `class` attribute values dictate different types of section. (an attribute is anything in an HTML tag that looks like `attribute="value"`). `</div>` simply denotes the end of a particular section (in fact, anything that looks like </ > is called a closing tag).

			<div class="panel home">
			</div>

4. Now let's fill the content section with actual content, by pasting the following between the `<div class="panel home">` and `</div>` tags.

	<h3>What does pre-assignment mean in general and to FroSoCo residents?</h3>
	<p>Pre-assignment is the process by which students can elect to opt out of the Housing Draw and commit to live in a specific house the following year. Some of Stanford's on-campus residences offer special academic, cultural, or social programs. Several residences sponsor foreign language study. Other residences support a &ldquo;cooperative lifestyle&rdquo;. In these houses known as &ldquo;co-ops&rdquo;, students do all the cooking and cleaning that maintain the house &amp; support its residents. In brief, the purpose of pre-assignment is to support and promote the unique academic, social, and cultural programs that many Stanford residences offer. Students who are genuinely interested in, and committed to, a program in a particular residence can &ldquo;pre-assign&rdquo; into that residence.</p>
	<p>For example, you can choose to stay in FroSoCo, and opt out of the Housing Draw, essentially building your own community of individuals that is committed to the lifestyle that FroSoCo offers.</p>
	<p>Any living spaces left vacant once pre-assignment comes to an end are then filled via the Draw. Though the Draw is not an entirely random process (it utilizes a priority system), it does not take into consideration the unique interests of students, or the various themes found across campus.</p>
	<p>By pre-assigning into FroSoCo and filling out a Residence Agreement, students bind themselves contractually to living in FroSoCo the following year, and so they cannot participate in the Housing Draw. Housing assignments for those who are pre-assigned are announced before the Draw.</p>
	<p>ALL students who pre-assign into FroSoCo will receive premium spaces, i.e. single rooms and two- room doubles, unless they prefer otherwise. More significantly, FroSoCo requires a Tier-3 housing option for pre-assignment, but still offers premium spaces. Generally, a Tier-3 housing option in the Draw will not result in students receiving premium rooms.</p>
	<h3>General requirements for pre-assignment</h3>
	<p>In order to apply for pre-assignment students must:</p>
	<ul>
		<li>Be a currently registered undergraduate student and be eligible for registration the autumn quarter for which they are applying</li>
		<li>Have a least one guaranteed year remaining at the time of the Draw</li>
		<li>Be free of any holds on their student record that would preclude them from being pre-assigned to the house</li>
		<li>Apply to be pre-assigned by the deadline and provide whatever documentation is required to support their application by that date</li>
		<li>Be willing to forfeit going through the Draw or accepting alternate Draw exempt staff positions</li>
	</ul>

5. The best way to understand what is going on is to open your web browser and see what tags produce what kinds of formatting and outputs.
	- <h3></h3> encloses subheadings (you can also try h1, h2, h3, ..., h6)
	- <p></p> encloses paragrahps
	- <ul></ul> encloses an unordered list
		- the "bullet points" of your list are each enclosed in <li></li> tags

6. Let's add a little more by including some interactivity (page links!). Add the following on the line right after the `</ul>` but before the last `</div>`. This code shows us how to create a link to another website!

			<h3>Are you ready to apply for pre-assignment?</h3>
			<p>You can apply for pre-assignment by submitting an application through the SAAS  website at <a href="http://saas.stanford.edu">(Click here)</a>.</p>
			<p>More Info: <a href="http://studentaffairs.stanford.edu/resed/profiles/theme/how-to-apply">http://studentaffairs.stanford.edu/resed/profiles/theme/how-to-apply</a></p>

7. Let's get even fancier and add a sidebar on the right-hand side. Add the following code after the last `</div>` (the very end of the page)

			<div id="sidebar">
				<h3>Useful links for information about pre-assignment and housing</h3>
				<p><a href="http://studentaffairs.stanford.edu/resed/profiles/theme/how-to-apply">Pre-Assignment Website</a></p>
				<p><a href="http://studentaffairs.stanford.edu/resed/profiles/theme/list">Review Theme House Requirements</a></p>
				<p><a href="http://studentaffairs.stanford.edu/resed/profiles/regular/govco/frosoco">FroSoCo's Information Page</a></p>
				<p><a href="http://saas.stanford.edu/">Pre-Assignment Application</a></p>
				<p><a href="http://www.stanford.edu/dept/rde/cgi-bin/drupal/housing/">Student Housing</a></p>
				<p><a href="http://www.stanford.edu/dept/rde/cgi-bin/drupal/housing/charts/draw-stats-2012">Undergraduate Housing Residence Chart 2011-12</a></p>
				<p><a href="http://houserank.stanford.edu">House Rank</a></p>
				<p>For questions about pre-assignment to FroSoCo, contact Mona Kitasoe (kitasoe@stanford.edu). You can also speak with the staff and/or CDs if you have questions.</p>
				<div class="alert alert-info">
					<p><strong>Downloads</strong></p>
					<p><a href="/assets/documents/2015-16FSCPreassignmentFAQs.pdf">2015-16 FSC Preassignment FAQs</a></p>
					<p><a href="/assets/documents/2015-16PreAssignInfo.pdf">2015-16 FSC Preassignment Info</a></p>
				</div>
			</div>

8. As you can see, we can have nested <div>'s, and you can think of them like nested sections. Be careful, though, because the child <div> will inherit the style of the parent <div> which can make things very confusing.

9. If you want to learn more, look into [Bootstrap](http://getbootstrap.com/examples/theme/) documentation to see what other awesome classes you can use. I would recommend just looking at existing pages on the FroSoCo website to see how they are built and formatted. Try using your browser's developer tools for even more powerful analysis of how pages are formatted.

##Part 3: Creating a Dynamic Webpage

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
- This was helpful because it had all of the relevant resident information that we need at different times of the year
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
		- email
		- bathroom flyers
		- hall white boards
		- signs on the exit doors
		- hall and house announcements
		- Facebook
- There could be a ton of others: instagram, snap chat, vines, a youtube channel, etc.