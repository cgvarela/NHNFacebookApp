# NHN FB Application

Bluemix provides a Node.js starter application as a template so that you can
add your code and push the changes back to the Bluemix environment. This template
along with the bootstrap blog template was combined to create the application. The
application will take posts, comments, upcoming events, and descriptions from a
Facebook Group and show them in a blog style layout on a webpage.

# Getting the app to run locally

* Need to get your Facebook Group's ID:
   The group ID value is retrieved from the home page of the Facebook group
   example: https://www.facebook.com/groups/<group ID value>
   
* Need to get the Facebook Group Token:
   The Facebook group token is retrieved after creating an app within Facebook itself
   and then getting a personal token. To create the Facebook app go to
   https://developers.facebook.com/ , click my apps -> new app and fill out the form
   to create your app and then you will be able to get the APP_ID and the APP_SECRET
   from the app's Dashboard.
   *No coding required, just creating the app in Facebook gives you the two values*

   Link to get personal token: https://developers.facebook.com/tools/explorer/145634995501895/ Make sure to check the user_events and user_managed_group permissions when getting the access token.

   To get the Group token use the following link with your three values plugged in:
   https://graph.facebook.com/oauth/access_token?client_id=<APP_ID>&client_secret=<APP_SECRET>&grant_type=fb_exchange_token&fb_exchange_token=<PERSONAL_TOKEN>
  
   The value given from the URL is the token which will last 60 days before needing
   to renew it (takes less then a minute once you have the APP_ID and APP_SECRET).
* Plug both the group ID and the token into app.js and your app should run.

* In the index.html and events.html file the name of the group, the about
  section and a short page description are hard coded in. To match up with the group
  you are pulling from you may want to update those values (they are plain text).
     
# Files

The NHNFB application has files as below:
* app.js
	This file contains the server side JavaScript code for your application
	written using the express server package.
* facebook.js
        This file contains the server side JavaScript code to perform the GET
        requests to the Facebook Graph API
* package.json
	This file contains metadata about your application, that is used by both
	the `npm` program to install packages, but also Bluemix when it's
	staging your application.  For more information, see:
	<https://docs.npmjs.com/files/package.json>
*manifest.yml
        This file is auto generated by Bluemix to help with staging the app.
* public/
	This directory contains public resources of the application, that will
	create the front-end of the app. The useFBData.js and useEventsFBData.js
        scripts are used to get the information that the back-end produces. The
        events.html file and the index.html file are used tie all of the data
        together that the scripts retrieved and produce the beautiful web page.

