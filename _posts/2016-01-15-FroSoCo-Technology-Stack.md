---
layout: post
title: "FroSoCo Technology Stack"
description: ""
category: tutorial
tagline: "Web Programming in PHP and CodeIgniter"
tags: [intermediate, web, php, codeigniter, datamapper]
---
{% include JB/setup %}

###Installation Prerequisites:
* [XAMPP Server 5.6.15](https://www.apachefriends.org/index.html) -- Cross platform local PHP/ Apache server with MySQL
* [Sublime Text 2](http://www.sublimetext.com/2) -- Cross platform development environment (to edit our code!)

###Technology Stack Overview
* [PHP 5.4.44](http://php.net/manual/en/index.php) -- Server scripting language
* [CodeIgniter 2.1.4](https://codeigniter.com/user_guide/)* -- Model-View-Controller web framework built on PHP
* [DataMapper ORM](http://datamapper.wanwizard.eu/pages/toc.html)* -- Easier database models
* [MySQL](http://dev.mysql.com/doc/refman/5.7/en/) -- The underlying database that stores our data
* [CodeIgniter Template Library](https://github.com/jenssegers/CodeIgniter-Template-Library)* -- Template engine to make our designs consistent


###Install and Open XAMPP
Right after successful installation, choose the option to open the XAMPP control panel before quitting the installer. To open the XAMPP Control Panel in the future, use:
* Mac: Applications > XAMPP > manager-osx
* Windows: Start | Programs | XAMPP


###Get Starter Code for FroSoCo Website
1. [Download starter code](https://github.com/frosoco/frosoco-starter/archive/master.zip)
2. Extract .zip file anywhere, but remember where you extract it to.
3. Click "Open Application Folder" in the XAMPP Control Panel (You will need to have started the control panel as indicated in the previous section)
4. Find and open the "htdocs" folder in this directory.
5. Delete all the contents of the "htdocs" folder.
6. Copy all of the files and folders from inside the unzipped folder from step 2 to "htdocs".

###Ruby Gems + Windows = frustration.
This part was annoying. Read my steps first, then use the information in the guides to help you install. My input is really only if you have significant problems.
I liked this [simple guide](http://www.testically.org/2012/02/02/installing-jekyll-and-ruby-on-windows/). If you're lucky, your installation of Ruby and DevKit will be painless, as the previous guide claims. Here's a more detailed, [official guide](https://github.com/oneclick/rubyinstaller/wiki/development-kit). Other guides made good attempts but failed in some parts by either having unnecessary complicated language OR not going into enough detail.

1. Make sure you have no other version of Ruby installed. UNINSTALL THAT STUFF NOW to avoid problems later.

2. Install Ruby using a [RubyInstaller](http://rubyinstaller.org/downloads/). If you're running 64-bit Windows 7, like I am, I recommend you download the [x86 RubyInstaller 2.0.0](http://rubyinstaller.org/downloads/), because I had some issue with running the Jekyll server on the 64-bit version of 2.0.0. You will want to check off "Add Ruby executables to your PATH" and "Associate .rb and .rbw files with this Ruby installation," unless you want to configure those yourself.

3. Then install the DevKit and have it extract all the files to anywhere, but remember the location because it is important.

4. Follow the instructions on the [official guide](https://github.com/oneclick/rubyinstaller/wiki/development-kit). BE VERY METICULOUS SO YOU DON'T HAVE TO REPEAT THINGS UNNECESSARILY.

5. config.yml should be in the DevKit folder (I used C:\Devkit). You can do a search on your computer if you forgot, like I did.

6. Follow the test case the official guide provides, which involves running this command: `gem install json --platform=ruby`. IF IT WORKS FINE, GO TO STEP 7.

7. [Troubleshoot](https://github.com/oneclick/rubyinstaller/wiki/Troubleshooting). I had some insane [problem exactly like this](https://groups.google.com/forum/#!topic/octopress/8pH9tJqiirA) with remnants of cygwin not allowing me to use `gem install json --platform=ruby` for the test case. When I ran `gem install jekyll --platform=ruby` it failed at installing fast-stemmer for the same reason as it failed the test case *before* it could even try to install jekyll.

8. Okay, now install Jekyll. Use `gem install jekyll --platform=ruby` (they recommend adding `--platform=ruby` in the official guide).

###Run the Jekyll Server!
This allows you to preview your website.

You have to be in the directory where your site files are, which is basically your YOUR_GITHUB_USERNAME.github.io folder, before you run `jekyll --server`. I made a .bat file to start the server easily without having to type the same commands in Command Prompt over and over.

    cd \PATH_TO_YOUR_SITE_FILES\YOUR_GITHUB_USERNAME.github.io
    jekyll serve

Then go to localhost:4000 to see your site.

Now you're on your own! Thankfully, [the guide](http://jekyllbootstrap.com/usage/jekyll-quick-start.html) at jekyllbootstrap.com makes easy to learn whatever else you need to know.

Edit: I updated October 24, 2013 to get rid of deprecated Jekyll commands. I also realized some instructions were not clear, so I fixed them up. Hopefully, it will be easy to understand.