Welcome to the HADataC wiki!

## Installing

#### SOLR-HADataC

#### HADataC-Console

The commands in the list below are supposed to be issued within the machine that is going to host the HADataC Console Code. The code is the Github project listed under hadatac.

Clone HADataC code from GitHub

You first need to verify that you have a `git` client in your machine. If not, you need to install one. Type the following command from your command line to see if you have git:

```git'''

Clone HADataC code 

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
