# Node-RED bundle

## Overview
![schema](https://github.com/tengu-team/bundle-node-red/blob/master/schema.png?raw=true)

## bundle components

This Bundle consists of three key components to start using our predefined dataflow of to start experimenting and create your own dataflows.

#### MonogDB
The Datastore used for this Bundle is MongoDB. This bundle had a specfic Database on MongoDB(Tengu-DB) which will be used to store all the data gathered from this dataflow. The Database is only accesible by using the provided Bundle-API. This API contains GET-calls to gather data from the Database.

#### ActiveMQ
Our predefined dataflow will gather information from a Messagebroker, ActiveMQ, where there is one topic(Tengu-Topic) which will be used to subscribe and send messages to. The messages that are received on the Tengu-Topic come from an RSS-feed of StackOverflow posts that have the following tags: `Java, Python, ActiveMQ or MongoDB`. The dataflow the subscribes to this specific topic and has a relation with the specific topic instead of with the whole service.

##### Available Interface
The Admin Panel of ActiveMQ is available at `http://x.x.x.x:8161` and uses basic auth to login. To Password is generated during the installation and will be visible in de status of the service.

#### Node-RED


## Usage

this bundle can be deployed in your juju environment by cloning this repo and clone the required charms that are not avilable on the juju charm store. to deploy this bundle use:

    juju deploy /path/to/bundle.yaml
