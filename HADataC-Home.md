# HADataC Documentation

## Installing

A basic HADataC installation involves the installation of a SOLR repository and a HADataC Console (i.e., the code hosted at this GitHub repository). The instructions below describe how to obtain and install these components, and test if the installation is working properly.

Before anything, however, we need to verify that the host machine has a `git client` to retrieve the code, and an `sbt` utility to run the console. In the command line of your machine, verify that you have a `git` client installed in your machine:

    git
 
If you don not have git, you need to install one: http://git-scm.com/downloads. Still from the command line, verify that you have `sbt` applications installed in your machine:

    sbt

If not, you need to install one: http://www.scala-sbt.org/.

#### SOLR-HADataC

#### HADataC-Console

Clone HADataC code from GitHub:

    git clone 

Set up HADataC configuration

Run sbt

Install that you have `sbt` installed. If not, install one

Execute `sbt`

Execute `run`

## Using

#### Web Console

Measurement Faceted Search

Measurement Spatial Search

Metadata Browser
 
HASNetO-Loader

HADataC-Loader

## Other HADataC Products

MOCCASN

## Publications

## Notes

## On August 7, 2015

* Git project 'hadatac-browser' was renamed to 'hadatac'. The new Git's URL for the code is https://github.com/paulopinheiro1234/hadatac.git

* activator was removed from the project. If you have your own activator, please feel free to use it but please DO NOT COMMIT a new activator into the project. The best way of running the code is through the use of sbt command line, which may be independently installed. From the command line, once you have sbt installed in your computer, you just need to type 'sbt' and then 'run' to activate hadatac (or even 'sbt run' if you are sure that sbt is not going to crash due to some change in your environment).

* Play!Authenticate has been integrated into HADATAC's web console. This means that HADATAC now has user management and authentication, as well as secure web navigation.

* We are close to complete the integration of SOLR into Play!Authenticate, which will allow HADATAC to persist its users inside of SOLR itself. We made the decision of storing user info into SOLR because we didn't want to have Postgres as the repository of HADATAC users. In other words, HADATAC has just one database system for everything that needs to be persisted (data, data summary, metadata including triple store, user management, etc).

* The first time you run HADATAC once you have updated it from the git repository (through a git clone), it will produce an error message asking for you to run a script. For now, it is fine for you to run this script, which generates the Postgres' schema for Play!Authenticate. Once the SOLR integration is complete, you will need to expand your SOLR schema to include user management, and thus avoid the annoying playAauthenticate error message. 
