---
layout: post
title: "Launching Day"
description: ""
category: tutorial
tagline: "Jekyll Bootstrap, Ruby, & Windows"
tags: [beginner, web, jekyll, code]
---
{% include JB/setup %}

Somehow, my experimenting created this monster. There's a sufficient amount of documentation regarding how to create your own static website with Jekyll/ Jekyll Bootstrap. But hopefully I can aggregate enough basic info to reduce the stress of dealing with an excessive amount of information - especially if you're new to front-end development. 


Out of these "prerequisites", I only knew the first one, so don't worry if you are a beginner:
- You should know how to use Git, the source control tool, and have it installed.
- You should be comfortable with HTML, CSS, and other languages for building websites.
- You should understand how to install a Ruby Gem.

###Github!
1. Create a GitHub account and [install GitHub](https://help.github.com/articles/set-up-git).
2. It should probably ask you where to put your GitHub folder. Put it somewhere you'll remember because that's where your repositories will be.
3. "Open a shell" in GitHub. I use some convoluted (but easy to understand) method where I open the GitHub GUI, Open an existing local repository, click "Tools", click "Open a shell here", and then use the cd command (change directory) to change my directory to the main GitHub folder. But, hey, it works...
4. **Follow [these steps](http://jekyllbootstrap.com/index.html#start-now) TO THE LETTER -- just do steps 1-2.**

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