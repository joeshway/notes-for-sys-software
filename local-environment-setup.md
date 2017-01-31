/********** Environment setup with Ubuntu 16.04 **********/

/****** Git ******/

/*** Setup ***/
Setup or login to an account with github
https://github.com/

join the unh-comp-698-system-sofware organization

open the git repository called notes and create a new repository by selecting the + icon in the top right

Add a repository name and leave all other settings alone

Click Create Repository and stay on the page that opens

open terminal and get to the folder you would like to store the local git files

Type git clone https://github.com/unh-comp-698-systems-software/notes.git

when done drop into the folder it creates and then the folder called notes

/****** Setup Docker in Ubuntu 16.04 ******/

/*** Install curl ***/
1. open terminal
2. type sudo apt-get update then hit enter
3. type then hit enter
	sudo apt-get install curl linux-image-extra-$(uname -r) linux-image-extra-virtual

/*** Set up Repository ***/
1.type then hit enter
	sudo apt-get install apt-transport-https ca-certificates

This allows apt to use a repository over HTTPS


2. type then hit enter
	curl -fsSL https://yum.dockerproject.org/gpg | sudo apt-key add -

This adds Docker's official GPG key



3. type then hit enter
	sudo add-apt-repository "deb https://apt.dockerproject.org/repo/ ubuntu-$(lsb_release -cs) main"

This sets up a stable repository

/*** install docker ***/
1. type then hit enter
	sudo apt-get -y install docker-engine

this instlled the latest version of docker

/*** test docker ***/
1. type then hit enter
	sudo docker run hello-world

This should return a meassage saying hello world, if you are seeing this then docker in setup correctly

/*** make sure docker will work for our needs ***/
1. type then hit enter
	docker run -it ubuntu:xenial /bin/bash

It should download some stuff.

It it worked you will be at a prompt that ends with /#

/********** End **********/
