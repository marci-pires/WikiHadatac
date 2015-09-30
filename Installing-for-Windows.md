## Installing HADataC on Windows

A basic HADataC installation involves the installation of a SOLR repository and a HADataC Console (i.e., the code hosted at this GitHub repository). The instructions below describe how to obtain and install these components, and test if the installation is working properly.

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. Open `git bash`. NOTE: If you do not have git, you need to install one: http://git-scm.com/downloads. 

In `git bash` on the command line, verify that you have `sbt` applications installed in your machine:

    $ sbt

If not, you need to install one: http://www.scala-sbt.org/.

##### What you will need
1. Java SDK 8+: http://java.com/en/download/ (or use your distribution's java)

Verify your Java version, by searching `about java' or typing the command below, it should show at least build 1.8.0. 

     $ javac -version

If something under this appears or the program fails, you need to properly install Java 1.8+

#### HADataC-Console

The HADataC Console code can be installed in any directory in your file system. Let assume that the HDataC Console is going to be installed in `/home/hadatac/'.You also need to have a distribution folder. Let assume that '/home/myfolder' is your distribution folder. Go to your distribution folder, and from there, clone HADataC code from GitHub:

    cd /home/myfolder/
    git clone https://github.com/paulopinheiro1234/hadatac.git

After downloading HADataC, your filesystem should have a new folder called /home/myfolder/hadatac. In this folder, go to your configuration folder inside hadatac (../hadatac/conf).

    cd /home/myfolder/hadatac/conf

#### Running the installation script

Set up the following HADataC configuration files:

    <edit> Application.conf
    <edit> hadatac.conf
    <edit> play-authenticate/mine.conf
    <edit> play-authenticate/smtp 

#### Running HADatAc Console

From your Run sbt

Install that you have `sbt` installed. If not, install one

Execute `sbt`

Execute `run`

