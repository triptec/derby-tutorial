Warning: WORK IN PROGRESS!
==========================

Okay so this is supposed to become some sort of a tutorial building a snippet app. I'll try to be as thorough, also I'm really new to Derby and this will be an attempt to learn.

I will start out with the derby-boilerplate repo and go from that.

Steps:
------

+1 Get derby-boilerplate
`$git clone git://github.com/switz/derby-boilerplate.git`
`cd derby-boilerplate`
`npm install`

Preliminary Steps:
------------------

+1 Install derby
+1.1 npm install derby (or maybe sudo npm -g install git://github.com/codeparty/derby.git#master?)
+1.2 derby new snippster (? open for better names but snippster.io is available)
+1.3 update packages.json to use edge && npm install
+1.4 maybe show the start app

+2 Start with the app
+2.1 Ripout the example app
+2.2 Create the model for a snippet
+2.2.5 Create a dummy snippet
+2.3 Create the collection of snippets
+2.3.5 Create a few dummy snippets

+3 Events
+3.1 Click and console.log or something like what snippet was clicked, possibly add a attribute of numClicked to the snippets
+3.2 Add form to create new snippets and remove snippets

+4 Routes?
+4.1 index, view, create

+5 Auth
+5.1 Add derby-auth

Reminder to self
----------------
Extras

sudo npm remove -g derby
sudo npm update npm -g
sudo npm cache clean
sudo npm install -g derby (or sudo npm -g install git://github.com/codeparty/derby.git#master)