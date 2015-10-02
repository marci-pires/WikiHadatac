A basic HADataC installation involves the following four steps:

* acquiring required software for installing/running the HADatAc Console

* downloading the HADataC Console code from this GitHub repository, and 

* executing its installation script. 

The instructions below describe how to obtain and install these components, and test if the installation is working properly.

## Step 1 : Acquiring Required Software

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. In the command line of your machine, verify that you have a `git` client installed in your machine:

    git
 
If you do not have git, you need to install one: http://git-scm.com/downloads. Still from the command line, verify that you have `sbt` applications installed in your machine:

    sbt

If not, you need to install one: http://www.scala-sbt.org/.

You will also need:

0. HADataC: https://github.com/paulopinheiro1234/hadatac
1. Java JDK 8: http://java.com/en/download/ (or use your distribution's java)
2. Solr 4.10.4: http://archive.apache.org/dist/lucene/solr/4.10.4/solr-4.10.4.tgz
3. Solr 5.2.1: http://archive.apache.org/dist/lucene/solr/5.2.1/solr-5.2.1.tgz
4. JTS Topology Suite: http://sourceforge.net/projects/jts-topo-suite/files/latest/download

## Step 2: Cloning HADatAc-Console

Be sure to clone our Git repository

    git clone https://github.com/paulopinheiro1234/hadatac.git

From now on, we assume that you cloned HADataC repository on your home directory ~. If you cloned somewhere else, be sure to change ~ for the desired location on your machine.

## Step 3: Running installation script

Go to the HADataC folder that has just been created through the execution of the '''git clone''' command above, and execute the installation script.
 
    cd hadatac
    ./install_hadatac.sh

## Step 4: Running HADataC

Most interaction with HADataC is through its web console. Since HADataC is both a web application and its own web server, you need to activate the server to enable the console in your browser. The first time you call sbt in your machine, it may be a while for the command below to respond -- it will be getting dependencies from the web.
 
    sbt run

Log to HADataC on your browser



    http://localhost:9000/hadatac/

Enjoy!
