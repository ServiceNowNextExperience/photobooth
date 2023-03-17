# Photobooth App
UI Builder (UIB) photobooth application

This is the main UX application that contains a page which will render the photobooth experience.

Open by navigating to UI Builder > Photobooth

**PRO TIP** Be sure to "Pull from repository" each time you start dev and it will make your life easier and you won't be having to stash all your changes every time I modify this readme before checking in your changes.

## Quick Start
Install the following dependencies into your instance then install this application.  The rendered page will be available at /now/photobooth/home

## Dependencies

1. Photobooth UIC Camera application
Install using **Studio**
https://github.com/ServiceNowNextExperience/photobooth-uic-camera
This contains the UI component that this application uses to interact with the camera and take snapshots.

2. Photobooth Core
https://github.com/ServiceNowNextExperience/photobooth-core
This App Engine Studio application is the core implementation for photobooth processes including tables, flows and a REST api endpoint for posting images to.

3. Photobooth App
https://github.com/ServiceNowNextExperience/photobooth/
Install the app from the repo you are in right now. 

## Try It
The main Photbooth App Home will be found at the path /now/photobooth/home/MyPB after installation.  "MyPB" refers to a record in the *Photobooth Instances* table.  If you don't have a record with a matching name then create one, again, matching the name in the path of the URL.

Once you have installed all three apps you can go test it.  Navigate to UI Builder and open the "Photobooth" app.  Click the "Open" icon in the URL bar at the top of the canvas.  You should see the Photobooth page with a blank image.  Click "Create Request" and enter a valid email address to enable the session, then use the slider to turn the camera on and take your first snap.

## Design Overview
The main Photobooth App relies on the Photobooth UIC Camera app to take the snapshots and the Photobooth Core app for tables and flows. When a new record is added to the Request table the web application will monitor with an AMB Record Watcher and initiate a snapshot, which is then sent back to the Core app via an API.

## Multi-camera Support
If you have multiple cameras you may specify the 65 character device id you would prefer to use (it will try to default to one).  To do so create a  Photobooth Instance record, open the URL for that photobooth (e.g. "MyPB" in /now/photobooth/home/MyPB) and open the developer tool inspector and look at the console.  You will see an event logged called "PHOTOBOOTH_CAMERA#AVAILABLE_CAMERAS_UPDATED" with an object having a "cameras" array.  Inspect that and copy and paste the device id to your Photbooth Instance record.
