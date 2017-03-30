A basic HADatAc installation involves the following four steps:

* acquiring required software for installing/running the HADatAc Console

* downloading the HADatAc Console code from this GitHub repository, and 

* executing its installation script. 

* (proxy setting if to be used on server)


## Step 1 : Acquiring Required Software

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. In the command line of your machine, verify that you have a `git` client installed in your machine:

    git
 
If you do not have git, you need to install one: http://git-scm.com/downloads. Still from the command line, verify that you have `sbt` applications installed in your machine:

    sbt

If not, you need to install one: http://www.scala-sbt.org/.

You will also need:

1. Java JDK 8: http://java.com/en/download/ (or use your distribution's java) (<b>MAKE SURE THE MACHINE IS NOT RUNNING JAVA 9</b>)
2. wget

## Step 2: Cloning HADatAc Code

The commands in this section are to be issued by root user

Create both /data and /data/git folders:

      mkdir -p /data/git

Go to git directory :

      cd /data/git

Once your are in your home directory (`~` is a shortcut for your home directory), clone HADatAc code by typing the following command:

      git clone https://github.com/paulopinheiro1234/hadatac.git

After cloning HADatAC, you should have a hadatac folder under your home directory. Go into the hadatac directory under your home directory by typing the following:

     cd /data/git/hadatac

## Step 3: Deploying HADatAc Database-dependencies

Once you are in /data/git/hadatac (you can check if you are in the right folder by typing `pwd`), type the following:

      ./production_install_hadatac.sh

This process will take a while so let it run. It will download and install a SOLR instance, a Blazegraph instance, and initialize the instance.

During the process of executing the script, you will be asked for an installation folder. Use <b>/data/hadatac</b> as installation folder

Open your browser to verify if the SOLR installation was successful
* Open another tab with the url: [http://localhost:8983/solr/](http://localhost:8983/solr/) 

Open your browser to verify if the Blazegraph installation was successful
* Open another tab with the url: [http://localhost:8080/bigdata/](http://localhost:8983/bigdata/) 

## Step 4: Deploying HADatAc

Go back to hadatac folder:

     cd /data/git/hadatac

Now type the following: 

     ./deploy_hadatac.sh

Browser open hadatac
url: [http://localhost:9000/hadatac/](http://localhost:9000/hadatac/)

Wait for page to open, it will take a while.

Finally, we need to setup the proxy configuration

     cd etc/apache2

in the /sites-available folder, add the following to the conf file:

     ProxyRequests Off

       <Proxy *>
               Order deny,allow
               Allow from all
       </Proxy>

       ProxyPass /hadatac http://127.0.0.1:9000/hadatac
       ProxyPassReverse /hadatac http://127.0.0.1:9000/hadatac