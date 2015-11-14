ControlKeys
===========

ControlKeys is a keyboard customization utility based on [Karabiner](https://pqrs.org/osx/karabiner).  If you are unfamiliar with Karabiner, you should check it out first.

What's wrong with Karabiner?
----------------------------

Nothing is wrong with Karabiner.  It's a very impressive, very powerful, and very useful utility.

Why did you fork Karabiner, then?
---------------------------------

Karabiner offers *a huge number* of options built-in, many of which I do not find useful.  I wanted to clean up the interface and offer only what I see as the best options.  Because Karabiner (and therefore ControlKeys) is so flexible that it allows the end user to create any customizations they want, it is not necessary to build them all into the utility.  I believe many of them would be a better fit for a wiki or some other repository of customization XML files.

Why rename your fork?  Why not just fork it and contribute back to the original project?
----------------------------------------------------------------------------------------

Because my goals are different.  If I write anything useful to Karabiner, I'd be thrilled to have them adopt my changes.  But many of my changes are probably not interesting to them.  (All changes that I think may be interesting are intended to go in the branch named `karabiner`.)

Karabiner can be thought of as though it has two parts:

1. the application, which offers the ability to reconfigure your input devices, and
2. a huge collection of configurations that you can apply or ignore, as you see fit.

Each configuration is probably there because *somebody* found it useful, but in many cases there are just two many of them.  For instance, take all the different approaches to giving your computer a Vim mode that you can use outside of Vim.  Rather than many competing Vim modes, why not offer one carefully chosen Vim mode?&mdash;of course with a variety of settings for finer-grained control of how the mode works.  By offering a curated collection of the best configurations, I hope to end up with a leaner and more user-friendly utility.


How to build
------------

System requirements:

* OS X 10.10+
* Xcode 6.0.1+
* Command Line Tools for Xcode
* Boost 1.56.0+ (header-only) http://www.boost.org/
* CocoaPods http://cocoapods.org/ (`sudo gem install cocoapods && pod setup`)

Please install Boost into `/opt/local/include/boost`. (eg. `/opt/local/include/boost/version.hpp`)

### Step 1: Getting source code

Download the source to master.tar.gz in the current directory, this can be re-executed to restart a cancelled download.

    curl -OLC - https://github.com/tekezo/Karabiner/archive/master.tar.gz

Extract the master.tar.gz file to "Karabiner-master" and delete the tar.gz file

    tar -xvzf master.tar.gz && rm master.tar.gz

### Step 2: Building a package

    cd Karabiner-master
    make

The `make` script will create a redistributable **ControlKeys-VERSION.dmg** in the current directory.


**Note:**
The build may fail if you have changed any environment variables or if you have modified scripts in the `/usr/bin` locations. Use a clean environment (new account) if this is the case.
