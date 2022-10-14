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

## Design Overview
