---
title: "Ubiquiti Unifi Controller"
date: 2018-11-14T16:30:00-05:00
weight: 15
---

This document covers how to setup netboot.xyz, a service that provides
iPXE-based installation and live boot of a bunch of operating systems,
on a Ubiquiti Unifi Controller managed network.
NOTE: Tested with a Unifi Security Gateway and the CloudKey and/or standalone controller and a "proxy" node running Docker, will also validate with tftp from USG/Cloudkey.

### Assumptions

I've made a few assumptions throughout this document that will probably be
different for your setup:

* You have a Unifi Controller available and updated to a recent release
* You have a machine that can run Docker or can SSH into the USG/Cloudkey
* You understand which network under Settings> Networks is your `LAN` that the machines you want to boot will be connected to
* The `LAN` connection has DHCP enabled and is managing the address assignment and other DHCP options

### Configure boot support in Unifi Controller

Open your Unifi Controller web portal.
Open Settings> Networks and click on "Edit" next to your `LAN` network where you want PXE.
