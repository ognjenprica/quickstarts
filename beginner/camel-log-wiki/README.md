camel-log-wiki: Demonstrates how to use logging with Camel
======================================================
Author: Fuse Team  
Level: Beginner  
Technologies: Camel  
Summary: This quickstart is the wiki example of the Camel Log quickstart which shows how to use logging in a simple Camel application  
Target Product: Fuse  
Source: <https://github.com/jboss-fuse/quickstarts>  


What is it?
-----------
This quickstart is the wiki example of the Camel Log quickstart which shows how to use logging in a simple Camel application  
It shows how to create a simple Apache Camel application that logs a message to the server log every 5th second.  
This example is implemented using solely the XML DSL (there is no Java code). The source code is provided in the following XML 
file `src/main/resources/OSGI-INF/blueprint/camel-log-wiki.xml`.
                                                   
This example uses a timer to trigger every 5th second, and then writes a message to the server log, as shown in the figure below:

https://github.com/fabric8io/quickstarts/blob/master/quickstarts/karaf/beginner/images/camel-log-diagram.jpg

As this is the wiki version of the log quickstart, the Camel route source code is defined in the profile only. You can edit the source code from within the web console, 
by selecting the `camel-log.xml` file in profile directory listing, which opens the Camel editor.

The editor allows you to edit the Camel routes, and have the running containers automatic re-deploy when saving changes.


System requirements
-------------------

Before building and running this quick start you need:

* Maven 3.1.1 or higher
* JDK 1.7 or 1.8
* JBoss Fuse 6


### This example requires creating a fabric.  To try it, follow the instructions below

* Start JBoss Fuse 6 by running bin/fuse (on Linux) or bin\fuse.bat (on Windows).
* In the JBoss Fuse console, enter the following command:
    
    fabric:create --wait-for-provisioning


### Building this example

The example comes as source code and pre-built binaries with the fabric8 distribution. 

To try the example you do not need to build from source first. Although building from source allows you to modify the source code, and re-deploy the changes to fabric. See more details on the fabric8 website about the [developer workflow](http://fabric8.io/gitbook/developer.html).

To build from the source code:

1. Change your working directory to `quickstarts/beginner/camel-log-wiki` directory.
1. Run `mvn clean install` to build the quickstart.
1. Run `mvn fabric8:deploy` to upload the quickstart to the fabric container.

If you run the `fabric:deploy` command for the first then, it will ask you for the username and password to login the fabric container.
And then store this information in the local Maven settings file. You can find more details about this on the fabric8 website about the [Maven Plugin](http://fabric8.io/gitbook/mavenPlugin.html).

## How to run this example

The following information is divided into two sections, whether you are using the command line shell in fabric, or using the web console

### Using the command line shell

You can deploy and run this example at the console command line, as follows:

1. It is assumed that you have already created a fabric and are logged into a container called `root`.
1. Create a new child container and deploy the `quickstarts-beginner-camel.log.wiki` profile in a single step, by entering the
 following command at the console:

        fabric:container-create-child --profile quickstarts-beginner-camel.log.wiki root mychild

1. Wait for the new child container, `mychild`, to start up. Use the `fabric:container-list` command to check the status of the `mychild` container and wait until the `[provision status]` is shown as `success`.

## How to try this example

1. Log into the `mychild` container using the `fabric:container-connect` command, as follows:

        fabric:container-connect mychild

1. View the container log using the `log:tail` command as follows:

        log:tail

To exit the tail logger, press Ctrl-D. And to logout from the `mychild` container, then use the `exit` command, which returns back to the `root` container.

## Undeploy this example

To stop and undeploy the example in fabric8:

1. Disconnect from the child container by typing Ctrl-D at the console prompt.
1. Stop and delete the child container by entering the following command at the console:

        fabric:container-stop mychild
        fabric:container-delete mychild


### Using the web console

You can deploy and run this example from the web console, as follows

1. It is assumed that you have already created a fabric and are logged into a container called `root`.
1. Login the web console
1. Click the Wiki button in the navigation bar
1. Select `quickstarts` --> `beginner` --> `camel.log.wiki`
1. Click the `New` button in the top right corner
1. In the Create New Container page, enter `mychild` in the Container Name field, and click the *Create and start container* button

## How to try this example
This example comes with sample data which you can use to try this example

1. Login the web console
1. Click the Containers button in the navigation bar
1. Select the `mychild` container in the containers list, and click the *open* button right next to the container name.
1. A new window opens and connects to the container. Click the *Logs* button in the navigation bar if the logs are not already displayed
1. You can also click the *Camel* button in the top navigation bar, to see information about the Camel application. 


## Undeploy this example

To stop and undeploy the example in fabric8:

1. In the web console, click the *Runtime* button in the navigation bar.
1. Select the `mychild` container in the *Containers* list, and click the *Stop* button in the top right corner

