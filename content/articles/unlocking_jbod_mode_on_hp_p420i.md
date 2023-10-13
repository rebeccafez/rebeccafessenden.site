+++
title = "Unlocking JBOD mode on an HP embedded P420i RAID card"
date = 2023-10-13
[taxonomies]
tags = ["servers", "homelab", "jbod"]
+++

I recently had a hard drive fail in my primary virtualization server. No matter,
HDDs are monsters that eat your data like candy, but lack of SMART reporting
meant that I didn't know the drive was going to fail until it just did. I took
this as a sign that I needed to finally figure out how to put the P420i RAID
card baked into the system board of my server into JBOD mode. It turns out that
this process is incredibly poorly documented, and multiple conflicting answers
exist on how to do this. This is what worked for me.

## Preparing the card

Enter HP SSA and delete all logical disks. If you have any logical disks,
hpssacli will refuse to put your card into JBOD mode.

## Setting up your environment

Download an ISO of a Debian based Linux distro. I recommend
[Linux Mint](https://linuxmint.com). Flash it onto a USB stick or attach it as
virtual media in iLO.

## Getting hpssacli

Once you have your Linux environment booted up, go to
[HPE's software repository](https://downloads.linux.hpe.com/SDR/repo/mcp/pool/non-free/)
and download `hpssacli-2.10-14.0_amd64.deb`. I have not tried this with other
versions of hpssacli, but this one worked on the first try.  
Next, install hpssacli:

```bash
sudo dpkg -i ./hpssacli-2.10-14.0_amd64.deb
```

## Using hpssacli

Once hpssacli is installed, change directory to `/opt/hp/hpssacli/bld`. In this
directory you should find the hpssacli binary. Use it to change the card mode:

```bash
./hpssacli controller slot=0 modify hbamode=on
```

Now you're done! If you do an `lsblk`, you should now see that all your drives
have been attached to the system individually. The trade-off with this process
is that you can no longer use any of the drives in the cage as a boot drive, but
this is not a problem at least for me, as my ML350p Gen8 has 3 additional SATA
ports on the motherboard.
