A basic HADataC installation involves the following four steps:

* acquiring required software for installing/running the HADatAc Console

* downloading the HADataC Console code from this GitHub repository, and 

* executing its installation script. 

The instructions below describe how to obtain and install these components, and test if the installation is working properly.

## Step 1: Acquiring Required Software

### Open terminal

Easiest method is to hit `command+spacebar > type > terminal > enter`.
This should open a terminal window that looks like a scary box where you put code.

### Install homebrew

Instructions for installation can be found here: [http://brew.sh/](http://brew.sh/) 

OR copy and paste this command in terminal: 

     ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

### Install sbt
In terminal type: 

     brew install sbt

Let that install. You may be prompted to install the xcode command line tools.
If so click `install` and let the installation finish before installing sbt again. 

### Install tar
In terminal type: 

     brew install tar

### Install wget
In terminal type: 

     brew install git

### Install git
In terminal type: 

     brew install tar

### Intall Java SDK 1.8+

Go to: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html 
Find the version you need (most likely for mac).

#### Download Java

Double click the orange package and install.
CHECK YOUR VERSION (on the terminal):

    javac -version 

You should see Java 1.8.0, the version you have just downloaded.
If not, you had a previous version. Proceed with the following steps to fix it: 

Run the following: 

      /usr/libexec/java_home -V

Check the versions and run: 

     export JAVA_HOME=`/usr/libexec/java_home -v <<java1.8 version from above>>`

Add the above line to the file ~/.bashrc to make the change permanent

## Step 2: Cloning HADatAc-Console

Google hadatac and find the github project, if you’re familiar with that process

It helps keep files up to date but requires at GitHub account
Or click the below link and a zip will download the file automatically.
https://github.com/paulopinheiro1234/hadatac/archive/master.zip

Once the files is downloaded unzip the .zip file and put the hadatac folder in your local directory.
You can get to your local directory by opening a finder window and clicking on your name in the navigation panel on the left. In terminal navigate to the hadatac folder (in terminal type): 

     cd ~/hadatac

`cd` is change directory. 

If you’re lost type: 

     pwd 

to find out where you are. 
If you want to list all the files and folders around you type: 

     ls 

If you want to get back to the start just type: 

     cd

## Step 3: Installing HADatAc

Once you are in the hadatac folder (you can check if you are in the right folder by typing `pwd`), type the following:

      ./install_hadatac.sh

This process will take a while so let it run. It will copy the files, download and install the two SOLR instances required by HADatAc, and initialize the instances.

## Step 4: Running HADatAc

Open your browser to verify if the SOLR installations were successful
Open one tab with the url: [http://localhost:7574/solr/](http://localhost:7574/solr/) 
Open another tab with the url: [http://localhost:8983/solr/](http://localhost:8983/solr/) 

Go back to terminal and type: 

     sbt

Note:Navigate to the hadatac folder using cd in the terminal window, before typing sbt
This step will take a long time the first time.

In the terminal window you should see `[hadatac]`
In the terminal window type: 

     run

Wait for confirmation message that the project is running.

Browser open hadatac
url: [http://localhost:9000/hadatac/](http://localhost:9000/hadatac/)

Wait for page to open, it will take a while.
