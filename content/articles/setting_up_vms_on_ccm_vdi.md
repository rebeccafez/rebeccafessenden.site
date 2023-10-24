+++
title = "Setting up VMs on CCM VDI"
date = 2023-10-23

[taxonomies]
tags = ["vdi", "virtualization"]
+++

In my Operating Systems and Utilities class, I've noticed some students have
trouble setting up VMs on the VDI provided by the school. What follows is a
tutorial on setting up an Ubuntu 22.04 LTS Desktop VM inside the ITLabs virtual
desktop.

## Logging into the VDI

Go to the VMware Horizon client if you're using a school computer, or the
[web client](studentview.ccm.edu) if you're not on campus. Enter your CCM
credentials. If you're using the web client, you will also need to authorize the
login in Microsoft Authenticator on your mobile device.

## Downloading an image

Download the latest
[live image](http://cdimage.ubuntu.com/jammy/daily-live/current/jammy-desktop-amd64.iso)
from Canonical for the desktop version of Ubuntu 22.04 LTS. The download should
take between 2 and 5 minutes.

## Creating a VM

Once the image has finished downloading, open VMware Workstation 16 Player. When
it asks for a license key, click on "non-commercial use." If any popups about
updates appear, ignore them.

Click on Create a New Virtual Machine. Select 'Installer disk image file
(iso)'.  
Click 'Browse'. Select the file you downloaded earlier.

The next screen will prompt for your full name, your username, and your
password. This does not actually do anything, and you can put whatever you want
here.

On the next screen, select the option to store the disk as a single file.

The final screen will show your configuration and ask you to confirm.

## Booting up the VM

When the VM boots up, it will ask a series of questions.

- Keyboard layout: US
- Installation Type: Erase disk and install Ubuntu
- Time Zone: New York
- Credentials: This is where you enter the username and password that you
  actually want to use.

After this, it's just a waiting game. When it finishes, allow it to reboot, and
you'll have an Ubuntu VM.
