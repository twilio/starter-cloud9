# Welcome to the Cloud9 Guild!

As members of the Cloud9 guild, you will be working through the challenges of TwilioQuest using the Ruby programming language and the Cloud9 browser-based IDE.  This project is pre-configured to do some interesting Twilio stuff using Ruby and the light-weight Sinatra web framework, and to be easily installable into the Cloud9 environment.

## Setting Up

Now we need to configure Cloud9 IDE to help us write Ruby code for our TwilioQuest.  The awesome part about Cloud9 is there is no software to dowload and install - we just need to sign up for an account and start writing code!

Your first step will be [signing up for a free account with Cloud9](https://c9.io/site/pricing/).  Once you have successfully signed up for an account, you must [go to your account dashboard from the home page](https://c9.io/).  On your dashboard, click "Create New Workspace":

![new workspace](http://demo.kevinwhinnery.com/upload/Dashboard_-_Cloud9-20130827-075733.png)

In the resulting popup, choose "Clone from URL":

![clone from URL](http://demo.kevinwhinnery.com/upload/Fullscreen-20130827-080032.png?bustgithubcache=true)

In the modal window, enter the URL for this repository, then click "Create":

![modal](http://demo.kevinwhinnery.com/upload/Dashboard_-_Cloud9-20130827-080236.png)

Cloud9 will take a few seconds to provision a new Ruby development environment for you.  During this time, you will be sent back to your dashboard, and will see your new project in the left-hand navigation with a "processing" indicator under it.  Once it is ready to use, the project name will appear in bold.  Click your new project to select it, and then click "Start Editing":

![new project](http://demo.kevinwhinnery.com/upload/Dashboard_-_Cloud9-20130827-080457.png)

This will bring you to the editor view.  This is where you will select and edit code files in your project, and where you will use the "terminal" to enter commands for Cloud9:

![Cloud9 IDE](http://demo.kevinwhinnery.com/upload/starter-cloud9_-_Cloud9-20130827-081045.png)

Now, let's configure and run your TwilioQuest app!

## Running the Application
Before we can actually run our app, we need to configure our development environment with a few pieces of information.  The first things we will need to configure are our Twilio "Account SID" and "auth token".  These are like our username and password for the Twilio API.  You can find these values [on your Twilio account dashboard](https://www.twilio.com/user/account).  If you haven't already, you will also need to [sign up for a Twilio account](https://www.twilio.com/try-twilio).

To configure your account SID, type the following command into the Terminal:

    export TWILIO_ACCOUNT_SID=your account sid

Which looks like:

![account sid](http://demo.kevinwhinnery.com/upload/starter-cloud9_-_Cloud9-20130827-081747.png)

Next, do the same for your auth token:

    export TWILIO_AUTH_TOKEN=your auth token

Which should look like:

![auth token](http://demo.kevinwhinnery.com/upload/starter-cloud9_-_Cloud9-20130827-081944.png)

The last bit of configuration you need to set up is your Twilio phone number.  When you signed up for an account, you should have been issued one.  You can reference this number, or buy a new number, [on this page in the admin console](https://www.twilio.com/user/account/phone-numbers/incoming).  Configure your Twilio phone number in the Terminal like this:

    export TWILIO_NUMBER=your twilio number

Which should look like:

![export number](http://demo.kevinwhinnery.com/upload/starter-cloud9_-_Cloud9-20130827-085227.png)

Now, we need to install our app's Ruby dependencies, which are distributed as Ruby Gems.  In most Ruby projects, these dependencies are specified in a "Gemfile".  To install the dependencies in our starter project's Gemfile, run the following command in the terminal:

    bundle install

After a few moments, you should see something like this:

![bundle install](http://demo.kevinwhinnery.com/upload/starter-cloud9_-_Cloud9-20130827-085515.png)

Now, we can finally run our project!  To launch our project from the terminal window, we run the following command, verbatim:

    ruby app.rb -p $PORT -o $IP

One launched, you should see output like this:

![run output](http://demo.kevinwhinnery.com/upload/starter-cloud9_-_Cloud9-20130827-090805.png)

Note the URL that is displayed on the last line - this is the address of your running web app on the public internet!  Open this URL in your web browser, and you should see something like:

![cloud9 guild](http://demo.kevinwhinnery.com/upload/Welcome_to_the_Cloud9_Guild%21-20130827-090940.png)

Now, you should be able to run through the voice and SMS demos on the page, after entering in your mobile phone number.

## Making Code Changes
During your quest, you'll probably be making code changes, tweaking this sample project to do interesting things with the Twilio API.  After editing files and changing code, you'll need to stop and restart your Ruby server.

To practice this, open `app.rb` in the Cloud9 editor.  Change the body of the text message sent for the "message" demo, [which happens on line 26](https://github.com/twilio/starter-cloud9/blob/master/app.rb#L26):

    # Use the REST API client to send a text message
    client.account.sms.messages.create(
      :from => TWILIO_NUMBER,
      :to => params[:to],
      :body => 'I edited some code!'
    )

To stop your server, click on the Terminal window of your Cloud9 IDE.  Then, hit control-C on your keyboard to stop the Ruby server.  This will cause your Ruby app to become unavailable on your public URL.  To restart the server, and observe your code changes in action, enter the same command you used ot start the server initially:

    ruby app.rb -p $PORT -o $IP

__TIP:__ Press "up" on your keyboard in the Terminal to recall your last command.  This will be faster than typing `ruby app.rb -p $PORT -o $IP` every time.

Now, navigate to your app's main web page and run the messaging demo.  You should now get a different message than you did the first time.  Repeat this process every time you change code in your application.

## Begin Questing!
This is but your first step into a larger world.  [Return to TwilioQuest](http://quest.twilio.com) to continue your adventure.  Huzzah!
