Wercker Demo
==========================================================

This project is a demo that uses wercker to build and deploy the app.  

## Overview

For this project we are going to be using a project created by [doomspark](https://github.com/doomspark) that
is [dropwizard](http://dropwizard.io/getting-started.html) and uses [Kotlin](http://kotlinlang.org).   

To view the license for this project please see [LICENSE](https://github.com/doomspork/kotlin-dropwizard/blob/master/LICENSE).    

## Build

To build this project we will use the maven image that is found on [docker hub](https://hub.docker.com/_/maven/).     

This project can be built locally using the wercker cli that you can get by following the installation instructions
[here](http://wercker.com/cli/install/), or just running this command.    

        curl -sSL http://wercker.io | sh -

Once you have the cli installed you will first need to login:    
      
        wercker login

You can then run the build (assuming you have a DOCKER_HOST value set) with the below command:   

        wercker build

## Deploy

This application will deploy to heroku, the version of heroku is just a sample, this can deploy to any deployment
environment that you choose.  

To test this deployment you will need to have the following environment variables setup.   

1. HEROKU_KEY - This is the API key you can get from Heroku account settings    
2. HEROKU_USER - This is your heroku username (likely an email)     
3. HEROKU_APP_NAME - The name of the app that this will deploy too.   

Once you have those enviornment variables defined you can test the deploy by running    

        wercker deploy

At this point your application should be able to be viewed by navigating to the url or running     

        curl http://$HEROKU_APP_NAME.herokuapp.com


