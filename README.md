# Android Development Environment #
This repository provides a development environment for Android apps and OS. 

## Requirements ##

* (Vagrant)[http://vagrantup.com]
* (VirtualBox)[https://www.virtualbox.org]
* (Vagrant Omnibus)[https://github.com/schisamo/vagrant-omnibus] (Installed via vagrant w/ `vagrant plugin install vagrant-omnibus`)

## Android Development ##
The development environment is intialized using vagrant. Once the requirements are installed, a `vagrant up` will download and configure everything needed for android development. You can access the environment with a `vagrant ssh`.

## Development ##

Currently most of the setup and configuration of the environment is performed by chef when vagrant provisions the VirtualBox VM, thus the configuration is in the kitchen, which is (a seperate git repository)[https://github.com/schlueter/kitchen] which has been added to this one as a subtree. Please sumbit any PR's to that repo.
