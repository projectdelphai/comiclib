comiclib
================

About
---------------
comiclib - projectdelphai@gmail.com

Written in Ruby, this program is meant to be a lightweight and fast comic organizer and reader
The first part of it (tfo) will organize, rename, and move all comics to a designated folder. The 
second part (tfr) will scan all the titles, add it to a database, and allows you to read them using
sxiv, a lightweight image viewer following vim shortcuts.
	
Setup
-----------
1. Dependencies
  * Gemfile
  * sqlite3
  * atool
  * sxiv
2. When first run, ~/.comiclib and ~/.comiclib/config.yml is created. The config file should be filled out first.
3. comiclib defaults to a main.db where the main library information is held. To create/use a new/different library specify it with -d <database name>. A new database file will be created at ~/.comiclib/<databasename>.db
4. A sample config file can be seen [here](http://pastebin.com/nGcY96Cu)
5. The file organizer is relatively stable but should be used with caution just in case

Notes/Features
--------------
1. comiclib has a gui feature where you can read unread comics. To use it, use the command 'comiclib maingui <options>'
2. In maingui, left-click reads the comics, right-click opens an information window, and middle-click marks it as read.
3. Keyboard shortcuts: r = reload, i = information, n = next set, p = previous set, o = options, <Right> and <Left> = move to next/previous comic
4. maingui is only for reading unread comics. To read already read comics, delete comics, clean library, or other features, use the command line.

Future Plans
------------------

* optionsgui
* add better error messages 
* Add a rename only config
* add developer configurations

Known Bugs
----------------
* [KINDA-FIXED] - On arch systems, ruby-gtk2 will not install properly. You will have to manually install it with
  "gem install gtk2"
* After a while of using the gui, the program will quit itself because of memory usage. Just restart. The command
  line interface has no such problems

Changelog
----------------

0.1.0
* Migrated from mysql to sqlite3
* Added support for multiple libaries
* Filled up documentation better

0.0.4-3
* fixed scanning
* edited so password failure doesn't create endless fail loop

0.0.4-2
* lowered memory usage
* fixed crash if there was no summary
* added thanks to comicvine editors and staff
* added checks for password, dropped support for yml password temporarily
* fixed organizer for breaks on letter v (yeah, it was weird)
* added proper reload after markasread
* fixed being able to move offscreen
* can now exit password query

0.0.4
* added basic gui using green shoes
* options menu to mark as read and view cover and title
* back and forward shortcuts to view all unread comics
* library cleaner upgrade (checks for jpg in database)
* create cover art for all comics in unread
* added mark as read button
* cli: "b" during any menu will go back up one level
* gui: "n" will go to next page of comics, "p" will go back, "i" will display info on highlighted comics,
	Left/Right (j/k) arrow key will highlist respective comic
* added refreshing after marking a comic as read
* manual refreshing shorcut: "r" (will refresh automatically however)
* added comicvine synopsis in info window
		

0.0.3-1
* added support for .cbz files
* checks if origdir is empty or not
* added error message for when all comics are moved to one folder

0.0.3
* removes deleted comics from database
* added times in logs
* logs library cleaning and comic moving
* clean library also alphabetizes and reorders comics
* can now manually delete comics

0.0.2
* added password switch
* packaged for arch linux
* if not exists, creates .comiclib directory

0.0.1
* combined tfo/tfr
* added tfo/tfr switches
* added switch for tfr firstrun
* add main menu if no switch
* creates custom yml if not existing

*******************************************
	DEV REMINDERS
*******************************************

* need to add dev production later
