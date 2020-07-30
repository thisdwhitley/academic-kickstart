---
title: "Time to rethink my home network"
subtitle: ""
date: 2020-07-30
type: "post"
tags: ["technology","home","network"]
categories: ["tech"]
showDisclosure: true
draft: true
---

I have not done much with my home network and it is starting to flake out, so
I'm going to use that as an excuse to rethink (read: overcomplicate) it.
<!--more-->

---

### BACKGROUND

I am currently just using the hardware that I got when I signed up for internet
through my cable provider.  I've been skeptical of this for a while now, but as
of late, my wifi keeps "dropping out."  By "dropping out," I mean, all of a
sudden all my wireless devices report that they've lost connectivity to the
internet.  However, my devices that are hardwired still have access...

This behavior is puzzling and I have done very little to troubleshoot, other
than unplug and replug the provided wifi router. I also called the cable company
and they suggested doing a factory reset on the router.  *I'm not going to do 
that.*

So I've purchased a (very humbly named)
[Ubiquiti UniFi Dream Machine](https://amzn.to/30VqyI4) because, well, because I
don't have a good reason here.  But it will allow for me to do some items that
I've been meaning to which will, undoubtedly, make things harder for myself.

---

### CHALLENGE

Here's a high level overview of my current network environment:

* cable modem (ISP provided)
* wifi router (ISP provided) [downstairs den]
* [UniFi Switch 8 POE-60W](https://amzn.to/3jV2QVd) [downstairs den]
* [UniFi AP-AC In Wall](https://amzn.to/33cBiF4) [downstairs office]
* [Raspberry Pi Model B Rev 1](https://www.raspberrypi-spy.co.uk/2012/09/raspberry-pi-board-revisions/):
  serving DHCP and DNS...

---

### SOLUTION

Having a more powerful wifi router will allow me to make some updates.  Some
things I'd like to accomplish (hopefully in upcoming posts):

* re-ip the entire network (10.8.26.0/24 is cute, but to avoid work IPs I will
  use 132.71.0.0/16)
* create different VLANs for infrastructure vs. IoT devices
* separate my DHCP and DNS services
* make it so that if my pi-hole goes down, it doesn't take **everything** down
* reduce reliance on my old ass raspberry pi
* incorporate some sort of secure DNS (be that DOH or DOT)
