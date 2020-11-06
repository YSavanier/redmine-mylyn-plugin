
# Contributing Guide

## Development environment - draft

1. Eclipse - at least Luna (4.4.x) 
- Plugn-in Development Environment (PDE)
- Maven Integration for Eclipse (m2e)
- AspectJ Development Tools (ADJT)
- m2e connector for ADJT
- m2e connector for Tycho

- to run within eclipse, it seems necessary to add org.apache.felix.scr to the list of required plugins in the run specificaiton.

## How to setup Redmine server for tests

Main goal is to ease plugin developers setup process of Redmine servers for tests - objectives:

* use technologies: VirtualBox, Vagrant, Puppet
* setup Redmine server with REST API enabled
* load with test data: sample users, projects, issues

Repository [https://github.com/ljader/redmine-mylyn-vagrant-boxes](https://github.com/ljader/redmine-mylyn-vagrant-boxes) contains scripts for Redmine test VMs.

TODO:

* figure out reliable static local IP assignment

### Redmine test VMs

**Important**: you must **MANUALLY** add IP to name mappings in hosts file!

* [http://vg-redmine26a.example.com/](https://github.com/ljader/redmine-mylyn-vagrant-boxes/tree/master/vg-redmine26.example.com)

## Performing a release

TODO Description based on [RoboVM Eclipse plugin - Performing a release](
https://github.com/robovm/robovm-eclipse/wiki/Performing-a-release)

## Supporting Java11+

Java 11 removes JAXB - http://www.descher.at/descher-vu/2019/01/java-11-jaxb-and-osgi/ and https://github.com/reficio/p2-maven-plugin

build a p2 repository with the necessary jars - suitable ones are not in orbit. It is possible to create this repository with 

   	mvn p2:site

in the java11deps directory, and then include this site into the target platform within eclipse for development, and when installing 
into the final user eclipse, the site can be used as an extra update site.


