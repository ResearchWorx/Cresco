![](images/cresco_logo.png)
======

Cresco is a free and open source edge computing framework.

## [Quick Start](QuickStart.MD)

#### Cresco Framework Core
 * [Cresco-Agent](https://github.com/ResearchWorx/Cresco-Agent): The main runtime which manages the loading of Cresco Plugins and logging.
 * [Cresco-Agent-Controller-Plugin](https://github.com/ResearchWorx/Cresco-Agent-Controller-Plugin): The main communications plugin for the Cresco Framework which establishes channels for message passing between agents in a tiered system. At this time this plugin is **required** for operation.
 
#### Cresco Framework Optional Plugins
 * [Cresco-SysInfo-Plugin](https://github.com/ResearchWorx/Cresco-SysInfo-Plugin): This plugin provides computational resource utilization for the machine hosting the Cresco Agent as messages sent back to a Global Controller.
 
#### Cresco Framework Example Plugins
 * [Cresco-Skeleton-Plugin](https://github.com/ResearchWorx/Cresco-Skeleton-Plugin): This project exists as a basic starting point for building a custom Cresco plugin.

#### Cresco Agent Topology
Cresco agents, through their Cresco-Agent-Controller-Plugin, arrange themselves into a hierarchy of a global, with a single controller, regions, each with a single regional controller, and a set of agents inside a region. The following diagram illustrates this hierarchy:

![](images/CrescoTopology.png)

This topology allows for distributed control, meaning that an agent controls its plugins, a region controls its agents and the global controls the regions over which it is in charge.

#### Getting Started
Getting started with Cresco is fairly simple, with steps as follows:
 1. Download/update/confirm a [Java Runtime Environment](http://www.oracle.com/technetwork/java/javase/overview/index.html) (JRE, Java Runtime) 1.7 or greater.
 2. Download the [latest agent build](http://128.163.188.129:9998/job/Cresco-Agent/lastSuccessfulBuild/com.researchworx.cresco$cresco-agent/) and [latest agent-controller plugin build](http://128.163.188.129:9998/job/Cresco-Agent-Controller-Plugin/lastStableBuild/com.researchworx.cresco$cresco-agent-controller-plugin/)
 3. Modify the configuration files for the agent and plugins (please refer to the wiki for configuration information)
 4. Run the agent with `java jar cresco-agent-<version>.jar -f <agent configuration file>`
 
#### Further Reading
For a more in-depth explanation of Cresco, you can read the author's [dissertation](http://uknowledge.uky.edu/cgi/viewcontent.cgi?article=1061&context=cs_etds).

#### Why the name Cresco?
 
* Proto-Indo-European *ker ("to grow"). 
* Old Armenian սերիմ (serim, "be born") and սերեմ (serem, "bring forth")
* Latin creare ("become visible, multiply, augment")
