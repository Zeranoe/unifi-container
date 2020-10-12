# UniFi Controller Container

A set of scripts to orchestrate a rootless UniFi Controller container. This
design uses stock container images (java:8 and mongo:3), and launches them in
a pod for shared network resources.

## Required Packages

* Binutils (for ar)
* Podman
* cURL

## Supported Platforms

These scripts should work on any OS that has Podman. It has been tested on
a Raspberry Pi 4 with Ubuntu 20.04 (64-bit) and Fedora 32.

## Usage

To download, create, and start everything:

`bash download && bash create && bash start`

Then to only start the existing Controller:

`bash start`

## Scripts

### download

Download the `unifi_sysvinit_all.deb` from Ubiquiti's site, extract it, and
organize it for the Java container.

### create

Create the pod, Java, and MongoDB containers. The pod itself is not started at
this point, till the `start` script is executed.

### start

Start the pod, thus bringing up the Java and MonogoDB containers.

### kill

Sends a signal to the pod, gracefully closing each container within.
