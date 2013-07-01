# SmartOS on Vagrant

SmartOS provides the best Node.js experience, and is an all-around powerhouse operating system.
Many developers use Vagrant to manage runtimes and build environments.

We want to bring an up to date version of SmartOS to Vagrant.

## Goals

1. to automate the *vagrant-ification* of a base smarts build
2. users should be able to get running with

		vagrant init smartos http://example/smartos-vagrant.box
		vagrant up
		vagrant ssh
	
3. The box should include *Nodejs* and all necessary build tools for compiling c++ node extensions
4. create an awesome single-page advertising how awesome smartos vagrant boxes are

## Plans

[Andrzej Szeszo](https://twitter.com/aszeszo) has provided a great head-start with his build scripts and running example.
We plan to expand upon this.

### Prepare Script

A prep-script should run on a clean SmartOS box. This box could be created with another script based on a build available at [smartos.org](https://smartos.org). Todos in no particular order:

- create a `vagrant` zone, the image UUID(version) should be configurable
- add nodejs packages to vagrant zone
- assign global and vagrant zones to use DHCP
- setup dns
- `vagrant ssh` should reach the vagrant guest zone, not the global zone
- the provisioning configuration in Vagrantfile should be reusable for deployment to SmartOS based hosting providers like Joyent

Ideally this could be a [packer](http://www.packer.io/) template but not sure yet if it can manage all the tasks.


