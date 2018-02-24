#### Cresco Docker Plugin Tester

This [archive](https://drive.google.com/open?id=1VI4hRfvneCqxZffuwDp687gMZpRntYxD) contains all the files necessary to test plugins in the current Cresco. Though no working 
knowledge of Cresco is required to run this container, some basic knowledge of Docker and Java 1.8 is
assumed; primarily involving building from a Dockerfile as well as compiling Maven projects.

To test, simply build the container from the Dockerfile using "docker build -t <container name>", which
will add all the included files into the container, and then run the container with 
"docker run <container name>". This will build a default Cresco Agent environment and load up a tester
plugin that is build from the [Cresco-Skeleton-Plugin](https://github.com/ResearchWorx/Cresco-Skeleton-Plugin).

To code a new plugin, simply clone the Cresco-Skeleton-Plugin repository and made the necessary code changes
to the start() method of the Plugin class. For further guidance, please review the Cresco documentation or
the source code of other existing plugins.

In order to test new plugins, copy the compiled JAR file into the plugins/ folder in this directory and amend 
the "plugins.ini" file to include a new entry matching the new plugin to test. The following new entries need
to be added:

_______________________________________________________________________________________________________________________________
```
[plugins]
plugin/1=1
plugin/2=1 <-------------- New Plugin Index Line, with "1" to indicate it's enabled on start

[plugin/0]
pluginname=cresco-agent-controller-plugin
jarfile=cresco-agent-controller-plugin.jar
discovery_secret_agent = cresco_docker_plugin_test
discovery_secret_region = cresco_docker_plugin_test
discovery_secret_global = cresco_docker_plugin_test
broker_username = test
broker_password = test

[plugin/1]
pluginname=cresco-skeleton-plugin
jarfile=cresco-skeleton-plugin-0.1.0.jar

[plugin/2] <-------------- Header Matching Index Line
pluginname=new-plugin <--- Matches <artifactID> in "pom.xml" file's Maven Assembly Plugin configuration
jarfile=new-plugin.jar <-- Matches the name of the .jar file in the plugins/ directory
```
_______________________________________________________________________________________________________________________________

Once the necessary changes have been made, simply re-build and re-run the Docker container to test the new plugin.

An example docker container can be found in the [Quick Start repository](https://hub.docker.com/r/crescoedgecomputing/quickstart/) on Docker Hub

