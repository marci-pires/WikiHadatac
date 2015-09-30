## Installing HADataC on Windows

A basic HADataC installation involves the following three steps:

1. acquiring required software for installing/running the HADatAc Console

2. downloading the HADataC Console code from this GitHub repository, and 

3. executing its installation script. 

The instructions below describe how to obtain and install these components, and test if the installation is working properly.

## Step 1: Acquiring required software 

### Acquiring Git

Verify that the host machine has a `git client` to retrieve the code. Open the '''cmd''' command to enter in the command mode. 

Open `git bash`. NOTE: If you do not have git, you need to install one: http://git-scm.com/downloads. 

### Acquiring SBT

In `git bash` on the command line, verify that you have `sbt` applications installed in your machine:

    $ sbt

If not, you need to install one: http://www.scala-sbt.org/.

### Acquiring Java SDK 1.8+

Verify your Java version, by searching `about java' or typing the command below, it should show at least build 1.8.0. 

     $ javac -version

If something under this appears or the program fails, you need to properly install Java 1.8+. If that is the case, go to  http://java.com/en/download/ (or use your distribution's java)

### Step 2: Downloading HADataC-Console

The HADataC Console code can be installed in any directory in your file system. Let assume that the HDataC Console is going to be installed in `/home/hadatac/'.You also need to have a distribution folder. Let assume that '/home/myfolder' is your distribution folder. Go to your distribution folder, and from there, clone HADataC code from GitHub:

    cd /home/myfolder/
    git clone https://github.com/paulopinheiro1234/hadatac.git

## Step 3: Running the installation script

Set up the following HADataC configuration files:

    <edit> Application.conf
    <edit> hadatac.conf
    <edit> play-authenticate/mine.conf
    <edit> play-authenticate/smtp 

### Running HADatAc Console

From your Run sbt

Install that you have `sbt` installed. If not, install one

Execute `sbt`

Execute `run`

