# RevengeOS #

<img src="https://raw.githubusercontent.com/RevengeOS/android_manifest/r9.0/RevengeOs-logo.jpg"> 

## Setting up your machine ##
### Manual Way ###

-- Grab Java 8:
```bash
$ sudo apt-get update
$ sudo apt-get install openjdk-8-jdk
$ sudo apt-get install openjdk-8-jre
```
-- Install build tools
```bash
sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl \
zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev \
x11proto-core-dev libx11-dev lib32z-dev ccache libgl1-mesa-dev libxml2-utils \
xsltproc unzip
```
NOTE: Arch Linux users, use the Arch wiki page to install your packages then
come back here: <a href="https://wiki.archlinux.org/index.php/Android#Building_Android
">Link to wiki</a>


###  Step Two: Configure Repo and Git  ###

NOTE: If you have any problems with the below commands, try running as root:
$ sudo -s

Git is an open source version control system which is incredibly robust for
tracking changes across repositories. Repo is Google's tool for working with Git
in the context of Android. More reading if you are interested:
<a href="https://source.android.com/source/developing.html
">Here</a>


Run these commands to get repo all working (only needed if you did the manual
method of setup above):
$ curl https://storage.googleapis.com/git-repo-downloads/repo > repo
$ chmod a+x repo
$ sudo install repo /usr/local/bin
$ rm repo

Then run these commands to get git all working:
```bash
$ git config --global user.name "Your Name"
$ git config --global user.email "you@example.com"
```

### Automatic Way (recommended!) ###

-- Grab a repo with some useful scripts, and run the needed one
```bash
$ sudo apt-get install git-core
$ git clone https://github.com/akhilnarang/scripts
$ cd scripts
$ ls$ bash setup/<script-name>
```
Run the script corresponding to your Linux Distribution:
arch-manjaro-apricity-build-environment-setup.sh - Arch based distros
ubuntu1604linuxmint18.sh - Ubuntu 16.04 or higher based distros
ubuntu1404.sh - Ubuntu 14.04
linuxmint17x.sh - Linux Mint 17.x

## Initializing Repo ##

```bash
# Create a directory for the source files
# You can name this directory however you want, just remember to replace
# WORKSPACE with your directory for the rest of this guide.
# This can be located anywhere (as long as the fs is case-sensitive)
$ mkdir WORKSPACE
$ cd WORKSPACE

# Install Repo in the created directory
# Use a real name/email combination, if you intend to submit patches
$ repo init -u https://github.com/RevengeOS/android_manifest -b r9.0
```

### Downloading the source tree ###

This is what you will run each time you want to pull in upstream changes. Keep in mind that on your
first run, it is expected to take a while as it will download all the required Android source files
and their change histories.

```bash
# Let Repo take care of all the hard work
#
# Tthe x on jx it's the amount of cores you have.
# 4 threads is a good number for most internet connections.
# You may need to adjust this value if you have a particularly slow connection.
$ repo sync -f --force-sync --no-clone-bundle -jx
```

### Building ###


```bash
# Go to the root of the source tree...
$ cd WORKSPACE
# ...and run the build commands.
$ . build/envsetup.sh
$ lunch
$ choose your device From the list
$ brunch device 
# For Eg Leeco Le max2 code name is x2 so brunch x2
```

## Thanks list ##

- <a href="https://github.com/LineageOS">LineageOS</a>
- 
- 
-

## Getting Help ##
 Please refer <a href="https://forum.xda-developers.com/chef-central/android/guide-android-rom-development-t2814763">this</a> guide from xda
 
 #### More Help ####
 Ask in  <a href="https://t.me/joinchat/HFzBDkV7S-P9oT5eEDO9RQ">Telegram Group</a>

