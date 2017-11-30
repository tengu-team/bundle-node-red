# Node-RED bundle

## Overview
![schema](https://github.com/tengu-team/bundle-node-red/blob/master/schema.png?raw=true)

## bundle components

This Bundle consists of three key components to start using our predefined dataflow of to start experimenting and create your own dataflows.

### MonogDB
The Datastore used for this Bundle is MongoDB. This bundle had a specfic Database on MongoDB(Tengu-DB) which will be used to store all the data gathered from this dataflow. The Database is only accesible by using the provided Bundle-API. This API contains GET-calls to gather data from the Database.

### ActiveMQ
Our predefined dataflow will gather information from a Messagebroker, ActiveMQ, where there is one topic(Tengu-Topic) which will be used to subscribe and send messages to. The messages that are received on the Tengu-Topic come from an RSS-feed of StackOverflow posts that have the following tags: `Java, Python, ActiveMQ or MongoDB`. The dataflow the subscribes to this specific topic and has a relation with the specific topic instead of with the whole service.

##### Available Interface
The Admin Panel of ActiveMQ is available at `http://x.x.x.x:8161` and uses basic auth to login. To Password is generated during the installation and will be visible in de status of the service.
![activemq](https://github.com/tengu-team/bundle-node-red/blob/master/ActiveMQ.png?raw=true)

### Node-RED
The Node-RED service will make it possible to easily create new dataflows or tweak the current predefined dataflow. To Deploy a certain dataflow on Node-Red we use a Node-RED deployer. This makes it possible to add as much workflows as desired. In that case the Node-RED deployer and the Node-RED service do not need to know all the other services that might be necessary to deploy a certain workflow. The Node-RED Deployer will install the required nodes that are needed to deploy a specific workflow.

##### Available Interface
In the Node-RED interface you can enable or disable debugging and logging on the current dataflow or you can create your own dataflow with data from thew Tengu-Topic or from another datasource like Twitter, RSS-feed...
![nodered](https://github.com/tengu-team/bundle-node-red/blob/master/Node-RED.png?raw=true)

## Usage

this bundle can be deployed in your juju environment by cloning this repo and clone the required charms that are not avilable on the juju charm store. to deploy this bundle use:

    juju deploy /path/to/bundle.yaml
