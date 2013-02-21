Warning: WORK IN PROGRESS!
==========================

Okay so this is supposed to become some sort of a tutorial building a snippet app. I'll try to be as thorough as possible, also I'm really new to Derby and this will be an attempt to learn.

I will start out with the derby-boilerplate repo and go from that.

For your information:

    node: v0.8.12
    npm: 1.2.12

Steps:
------

###1.0 Get derby-boilerplate and install all dependensies and get the app running

Okay, crack up a terminal and run the following commands to clone the boilerplate repo and then cd into it and run npm to install all the dependensies of the repo, this will install derby and many other modules.


    $git clone git://github.com/switz/derby-boilerplate.git    
    $cd derby-boilerplate
    $npm install
    $node server.js

On this last step you should have ended with a Error like

`Error: OAuth2Strategy requires a clientID option`

This is due to those lines of code in ./src/server/index.coffee

    # Authentication setup
    strategies =
      facebook:
        strategy: require("passport-facebook").Strategy
        conf:
          clientID: process.env.FACEBOOK_KEY
          clientSecret: process.env.FACEBOOK_SECRET

More specific the last two lines, they try to get a facebook application key and secret. So goto http://developers.facebook.com and create a application and get the app cridetials.

So now we start the app with

    $FACEBOOK_KEY='<your fb key>' FACEBOOK_SECRET='<your fb secret>' node server.js

So now we have a second error:

`Error: failed to connect to [localhost:27017]`

This is due to the application trying to connect to a mongodb server. So get over to their site and follow the instructions and install one. Then open a second terminal and start it with:

    $sudo mongod

And get back to your other terminal and start the app again!

    $FACEBOOK_KEY='<your fb key>' FACEBOOK_SECRET='<your fb secret>' node server.js

Now your derby server should be running, head on over to http://localhost:3000 an lo and behold you should see a login form and a register form.

#####Sidenote:

I got this when I started it but I just tried again and it worked

Error:

    timers.js:103
                if (!process.listeners('uncaughtException').length) throw e;
                                                                          ^
    Error: Model bundling took longer than 1000 ms
        at Object.onBundleTimeout [as _onTimeout] (/Users/frasse/Documents/Development/Node.js/derby/snippster.io/node_modules/racer/lib/bundle/bundle.Model.js:63:9)
        at Timer.list.ontimeout (timers.js:101:19)


Preliminary Steps:
------------------

+   1 Install derby
+   1.1 npm install derby (or maybe sudo npm -g install git://github.com/codeparty/derby.git#master?)
+   1.2 derby new snippster (? open for better names but snippster.io is available)
+   1.3 update packages.json to use edge && npm install
+   1.4 maybe show the start app

+   2 Start with the app
+   2.1 Ripout the example app
+   2.2 Create the model for a snippet
+   2.2.5 Create a dummy snippet
+   2.3 Create the collection of snippets
+   2.3.5 Create a few dummy snippets

+   3 Events
+   3.1 Click and console.log or something like what snippet was clicked, possibly add a attribute of numClicked to the snippets
+   3.2 Add form to create new snippets and remove snippets

+   4 Routes?
+   4.1 index, view, create

+   5 Auth
+   5.1 Add derby-auth

Reminder to self
----------------

Extras

`$sudo npm remove -g derby`

`$sudo npm update npm -g`

`$sudo npm cache clean`

`$sudo npm install -g derby (or sudo npm -g install git://github.com/codeparty/derby.git#master)`