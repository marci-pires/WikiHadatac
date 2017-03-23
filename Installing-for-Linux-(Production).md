A basic HADataC installation involves the following four steps:

* acquiring required software for installing/running the HADatAc Console

* downloading the HADataC Console code from this GitHub repository, and 

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

      mkdir -R /data/git

Go to git directory :

      cd /data/git

Once your are in your home directory (`~` is a shortcut for your home directory), clone HADatAc code by typing the following command:

      git clone https://github.com/paulopinheiro1234/hadatac.git

After cloning HADatAC, you should have a hadatac folder under your home directory. Go into the hadatac directory under your home directory by typing the following:

     cd /data/git/hadatac

## Step 3: Installing HADatAc

Once you are in the hadatac folder (you can check if you are in the right folder by typing `pwd`), type the following:

      ./install_hadatac.sh

This process will take a while so let it run. It will copy the files, download and install the two SOLR instances required by HADatAc, and initialize the instances.

During the process of executing the script, you will be asked for an installation folder. Use <b>/data/hadatac</b> as installation folder

Open your browser to verify if the SOLR installations were successful
* Open another tab with the url: [http://localhost:8983/solr/](http://localhost:8983/solr/) 

## Step 4: Running HADatAc

Go back to terminal, and go to your installation folder by typing the following, after making sure that you replace the `(your hadatac installation directory)` by your actual hatadac installation directory:

     cd (your hadatac installation directory)

Now type the following: 

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

If you are installing hadatac on the server, you would also want to do the proxy setting
go to the apache folder on your server, for example:

     cd etc/apache2

in the /sites-available folder, add the following to the conf file:

     ProxyRequests Off

       <Proxy *>
               Order deny,allow
               Allow from all
       </Proxy>

       ProxyPass /hadatac http://127.0.0.1:9000/hadatac
       ProxyPassReverse /hadatac http://127.0.0.1:9000/hadatac