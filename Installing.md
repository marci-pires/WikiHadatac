## Installing HADataC

A basic HADataC installation involves the installation of a SOLR repository and a HADataC Console (i.e., the code hosted at this GitHub repository). The instructions below describe how to obtain and install these components, and test if the installation is working properly.

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. In the command line of your machine, verify that you have a `git` client installed in your machine:

    git
 
If you don not have git, you need to install one: http://git-scm.com/downloads. Still from the command line, verify that you have `sbt` applications installed in your machine:

    sbt

If not, you need to install one: http://www.scala-sbt.org/.

#### SOLR-HADataC

Let assume that SOLR-HADataC is going to be installed in a SOLR_HOME folder, e.g., `/home/mysolr/'.

[HENRIQUE] Where do we get SOLR 4 (4.10.x) 

[HENRIQUE] Where do we get SOLR 5 (5.x)

For the SOLR repository for HADataC (SOLR-HADataC), we assume that you have already the following:
- A SOLR instance version 4.10.x
- A SOLR instance version 5.x (optional, if you want a newer version to store the data and dynamic metadata)

If you do not have SOLR already up and running, you can follow the instructions on the official Apache SOLR website here - https://cwiki.apache.org/confluence/display/solr/Taking+Solr+to+Production.

[Henrique] HOW I UNZIP the TAR FILES?

[Henrique] DO I NEED TO RUN SOME SCRIPT, MAKE, ETC?

[Henrique] HOW DO I SET UP THE PORTS?

[Henrique] HOW TO I EXEC SOLR (AND WHERE DO I ASSIGN PORTS 7574 TO SOLR4 and PORT 8983 TO SOLR5?

HADataC defaults to the following:
- SOLR 4.10.x runs on port 7574
- SOLR 5.x runs on port 8983

[Henrique] HOW DO I KNOW IF SOLR4 and SOLR5 are properly installed and running?

[Henrique] HOW TO I STOP SOLR? 

##### Installing SolRDF module

First clone our solr-hadatac github

    git clone https://github.com/hansidm/solr-hadatac.git

Then move the contents of solrdf-home to your SOLR_HOME for the SOLR 4.10.x directory and set the right permissions (the code below user /var/solr4/data as SOLR_HOME and user solr as the solr user)

    cd solr-hadatac/solrdf-home
    sudo cp -R * /var/solr4/data
    sudo chown -R solr /var/solr4/data

##### Installing HADataC collections for data and dynamic metadata

Next, move the contents of solr-home to your SOLR_HOME to either your SOLR 4.10.x or SOLR 5.x if you decided to use a newer version

    cd ../solr-home
    sudo cp -R * /var/solr/data
    sudo chown -R solr /var/solr/data

To finish, restart the used SOLR instances

    sudo service solr restart
    sudo service solr4 restart

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

