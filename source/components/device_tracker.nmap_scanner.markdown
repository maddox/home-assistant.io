---
layout: page
title: "Nmap support"
description: "Instructions how to integrate Nmap into Home Assistant."
date: 2015-03-23 19:59
sidebar: false
comments: false
sharing: true
footer: true
---

<img src='/images/supported_brands/network-workgroup.png' class='brand pull-right' />
As an alternative to the router-based device tracking, it is possible to directly scan the network for devices by using Nmap. The IP addresses to scan can be specified in any format that Nmap understands, including the network-prefix notation (`192.168.1.1/24`) and the range notation (`192.168.1.1-255`).

If you're on Debian or Ubuntu, you might have to install the packages for arp and nmap. Do so by running `apt-get install net-tools nmap`.

```
# Example configuration.yaml entry
device_tracker:
  platform: nmap_tracker
  hosts: 192.168.1.1/24
```

See the [device tracker component page](/components/device_tracker.html) for instructions how to configure the people to be tracked.
