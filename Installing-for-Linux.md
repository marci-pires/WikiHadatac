## Installing HADataC on Linux/MacOS

A basic HADataC installation involves the installation of a SOLR repository and a HADataC Console (i.e., the code hosted at this GitHub repository). The instructions below describe how to obtain and install these components, and test if the installation is working properly.

#### What you will need

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. In the command line of your machine, verify that you have a `git` client installed in your machine:

    git
 
If you do not have git, you need to install one: http://git-scm.com/downloads. Still from the command line, verify that you have `sbt` applications installed in your machine:

    sbt

If not, you need to install one: http://www.scala-sbt.org/.

You will also need:

0. HADataC: https://github.com/paulopinheiro1234/hadatac
1. Java VM 7+: http://java.com/en/download/ (or use your distribution's java)
2. Solr 4.10.4: http://archive.apache.org/dist/lucene/solr/4.10.4/solr-4.10.4.tgz
3. Solr 5.2.1: http://archive.apache.org/dist/lucene/solr/5.2.1/solr-5.2.1.tgz
4. JTS Topology Suite: http://sourceforge.net/projects/jts-topo-suite/files/latest/download

Be sure to clone our Git repository

    git clone https://github.com/paulopinheiro1234/hadatac.git

From now on, we assume that you cloned HADataC repository on your home directory ~. If you cloned somewhere else, be sure to change ~ for the desired location on your machine.

#### SOLR-HADataC

We assume that SOLR-HADataC is going to be installed as 'unmanaged services', i.e., manually taken up and down by the user. For installation as managed service, you need administrative privileges on the machine as well as knowledge about your internal network, like available ports, firewalls and such. Follow this link for more information [link].

##### Download Solr

    cd ~
    wget http://archive.apache.org/dist/lucene/solr/4.10.4/solr-4.10.4.tgz
    wget http://archive.apache.org/dist/lucene/solr/5.2.1/solr-5.2.1.tgz

##### Uncompress Solr 4.10.4

    cd ~
    tar xvfz solr-4.10.4.tgz

##### Uncompress Solr 5.2.1

    cd ~
    tar xvfz solr-5.2.1.tgz

##### Run Solr services

The GitHub you cloned in the beginning of these instructions comes with ready out-of-the-box scripts for Solr startup. They assume that you cloned HADataC and uncompressed Solr on your home directory. If not, make sure do update the scripts to your needs (you will need to review the paths on the following files: run_solr4.sh, run_solr5.sh, solr4.in.sh and solr4.in.sh).

First, make the scripts executable to you:

    cd ~/hadatac/hadatac.solr
    chmod u+x *.sh

After that, you can start your instances by issuing:

    ./run_solr4.sh start
    ./run_solr5.sh start

You can also change the command start to stop or restart to stop or restart the instances.

##### Install JTS on Solr 5

HADataC makes use of JTS Topology Suite to provide spatial capabilities. Download it from the link below and copy the lib to your lib folder of Solr 5.

    cd ~
    unzip jts-1.13.zip
    cd jts-1.13/lib
    cp * ~/solr-5.2.1/server/solr-webapp/webapp/WEB-INF/lib

Restart Solr 5 to make it see that libs

    cd ~/hadatac/hadatac.solr
    ./run_solr5.sh restart

##### Verify Solr installation

Verify that Solr 4.10.4 is running by pointing you browser to [http://localhost:7574/solr](http://localhost:7574/solr). You should see Solr administrative interface with some information. Check if the collection is loaded by clicking 'Core admin' on the left and you should see the 'store' collection listed.

Verify that Solr 5.2.1 is running by pointing you browser to [http://localhost:8983/solr](http://localhost:8983/solr). You should see Solr administrative interface with some information. Check if the collections are loaded by clicking 'Core admin' on the left and you should see both 'sdc' and 'measurement' collections listed.

#### HADataC-Console

The HADataC Console code can be installed in any directory in your file system. Let assume that the HDataC Console is going to be installed in `/home/myfolder/'. We need to go to the installation folder, and from there, clone HADataC code from GitHub:

    cd /home/myfolder/
    git clone https://github.com/paulopinheiro1234/hadatac.git

After downloading HADataC, your filesystem should have a new folder called /home/myfolder/hadatac. In this folder, go to your configuration folder inside hadatac (../hadatac/conf).

    cd /home/myfolder/hadatac/conf

Set up the following HADataC configuration files:

    <edit> Application.conf
    <edit> hadatac.conf
    <edit> play-authenticate/mine.conf
    <edit> play-authenticate/smtp 

From your Run sbt

Install that you have `sbt` installed. If not, install one

Execute `sbt`

Execute `run`

