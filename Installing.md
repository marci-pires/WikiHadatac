## Installing HADataC

A basic HADataC installation involves the installation of a SOLR repository and a HADataC Console (i.e., the code hosted at this GitHub repository). The instructions below describe how to obtain and install these components, and test if the installation is working properly.

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. In the command line of your machine, verify that you have a `git` client installed in your machine:

    git
 
If you don not have git, you need to install one: http://git-scm.com/downloads. Still from the command line, verify that you have `sbt` applications installed in your machine:

    sbt

If not, you need to install one: http://www.scala-sbt.org/.

#### SOLR-HADataC

We assume that SOLR-HADataC is going to be installed in a directory, e.g., '/home/user/solr' as 'unmanaged services', i.e., manually taken up and down by the user. For installation as managed service, you need administrative privileges on the machine as well as knowledge about your internal network, like available ports, firewalls and such. Follow this link for more information [link].

##### What you will need
1. Java VM 7+: http://java.com/en/download/ (or use your distribution's java)
2. Solr 4.10.4: http://archive.apache.org/dist/lucene/solr/4.10.4/solr-4.10.4.tgz
3. Solr 5.2.1: http://archive.apache.org/dist/lucene/solr/5.2.1/solr-5.2.1.tgz

Verify your Java version, it should show at least 1.7.0. If something under this appears or the program fails, you need to properly install Java 1.7+.

    java -version

##### Download Solr

    cd ~/solr
    wget http://archive.apache.org/dist/lucene/solr/4.10.4/solr-4.10.4.tgz
    wget http://archive.apache.org/dist/lucene/solr/5.2.1/solr-5.2.1.tgz

##### Uncompress and run Solr 4.10.4

    cd ~/solr
    tar xvfz solr-4.10.4.tgz
    cd solr-4.10.4
    bin/solr start -p 7574

Verify that Solr 4.10.4 is running by pointing you browser to http://localhost:7574/solr. You should see Solr administrative interface with some information.

##### Uncompress and run Solr 5.2.1

    cd ~/solr
    tar xvfz solr-5.2.1.tgz
    cd solr-5.2.1
    bin/solr start -p 8983

Verify that Solr 5.2.1 is running by pointing you browser to http://localhost:8983/solr. You should see Solr administrative interface with some information.

##### Install SOLR-HADataC static metadata collection

First git clone our collections repository

    cd ~/solr
    git clone https://github.com/hansidm/solr-hadatac.git

Copy the contents of solrdf-home to your Solr 4.10.4 instance

    cd solr-hadatac/solrdf-home
    cp -R * ~/solr/solr-4.10.4/example/solr/

Restart Solr 4.10.4

    cd ~/solr/solr-4.10.4
    bin/solr restart -p 7574

Check if the collection is loaded by pointing your browser to http://localhost:7574/solr and it should show no errors on the top. Click 'Core admin' on the left and you should see the 'store' collection listed.

##### Install SOLR-HADataC dynamic metadata and data collections

Copy the contents of solr-home to your Solr 5.2.1 instance

    cd ~/solr/solr-hadatac/solrdf-home
    cp -R * ~/solr/solr-5.2.1/server/solr/

Restart Solr 5.2.1

    cd ~/solr/solr-5.2.1
    bin/solr restart -p 8983

Check if the collection is loaded by pointing your browser to http://localhost:8983/solr and it should show no errors on the top. Click 'Core admin' on the left and you should see both 'sdc' and 'measurement' collections listed.

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

