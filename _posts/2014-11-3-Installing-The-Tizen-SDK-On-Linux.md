---
layout: post
title: Installing The Tizen SDK On Linux
published: true
categories: linux, android, programming
---

Before starting the installation, check the prerequisites.

https://developer.tizen.org/downloads/sdk/installing-sdk/prerequisites-tizen-sdk

I got off and downloaded the tizen SDK and the tizen SDK Wearable from their download page. (tizen-sdk_2.3.57_ubuntu-64.bin)

https://developer.tizen.org/downloads/tizen-sdk#installmanager

After downloading the bin file run

chmod +x tizen-sdk_2.3.57_ubuntu-64.bin

and then 

./tizen-sdk_2.3.57_ubuntu-64

this command as it happened didn't give any thing meaningful, instead it showed an error

OpenJDK is not supported. Try again with Oracle JDK. 

Upon searching for a solution, I realized I needed java oracle in order to run the tizen manager. Found the solution at http://www.webupd8.org/2012/09/install-oracle-java-8-in-ubuntu-via-ppa.html webupd8 which enable me to install the oracle jdk for developmeny through a ppa

sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer

