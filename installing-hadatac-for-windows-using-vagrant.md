# Installing-HADATAC-for-Windows-Using-Vagrant

We use VirtualBox and Vagrant to create a virtual machine \(VM\) on windows and install HADATAC on the VM.

To install hadatac on windows, we need to do the steps below: 1. Install required software for creating a local VM 2. Configure and create a VM. 3. Deploy environment in VM. 4. Install HADATAC.

## Step 1: Install software on Windows

We need VirtualBox, which enables us to create VM, and Vagrant, which is a console-based frontend of VirtualBox.

If VirtualBox is not installed, you can download one from: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads) and install it.

After installation of Virtual, you can download Vagrant from: [https://www.vagrantup.com/downloads.html](https://www.vagrantup.com/downloads.html) and install it.

## Step 2: Configure and Create a local VM

Create a local file folder to hold the VM, and we call it {VM\_Directory}.

My example: `{VM_Directory} = F:\hadatacVM`

Access Windows Command Console by pressing Windows+R and enter cmd Navigate to {VM\_Directory} in cmd console.

My example:

```text
F:
cd hadatacVM
```

To Create the config file of VM of Ubuntu 16.04LTS, run in console: `vagrant init ubuntu/xenial64`

Run `curl https://raw.githubusercontent.com/paulopinheiro1234/hadatac/master/Vagrantfile > Vagrantfile` in the command line to get the modified vagrant file needed for compatibility with HADATAC.

Next, go back to console, navigate to the VM Directory, and run: `vagrant up`

After the VM is up, you can ssh to it by: `vagrant ssh`

## Step 3: Deploy the environment in VM

Install the required software: `sudo apt update`

To install git, run: `sudo apt install git`

To install wget, run: `sudo apt install wget`

To install unzip, run: `sudo apt install unzip`

To install jdk, run: `sudo apt install default-jdk`

To install sbt, run:

```text
echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
sudo apt update
sudo apt install sbt
```

## Step 4: Install HADATAC

Continue from install instructions \[1.2 Step 2 \]\([https://github.com/paulopinheiro1234/hadatac/wiki/1.2.-Installing-for-Linux-\(Developer](https://github.com/paulopinheiro1234/hadatac/wiki/1.2.-Installing-for-Linux-%28Developer)\)\).

