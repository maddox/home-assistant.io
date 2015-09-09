---
layout: page
title: "Advanced Raspberry Pi setup"
description: "Advanced instructions for running Home Assistant on a Raspberry Pi."
date: 2015-09-08 22:46
sidebar: false
comments: false
sharing: true
footer: true
---

### {% linkable_title Setting up a background service %}

If you would like to run `hass` as a background process on the Raspberry Pi, you can run the following command:

```bash
nohup hass </dev/null 1>&2&> nohup.log &
```

This will launch Home Assistant as a background process and continue to run even after disconnecting from a terminal session.

To shut down Home Assistant, you can use the `homessistant/stop` service using the 'Call Service' developer tool (first icon in sidebar).

<p class='note'>
Make sure your Home Assistant installation is working correctly before trying to launch as a background process. You can use <code>tail -f ~/.homeassistant/home-assistant.log</code> to review any errors or <code>tail -f ~/nohup.log</code> to view a more verbose version.  You can press CTRL-C to exit either of the logs.
</p>

### {% linkable_title Optimizing memory %}

If you are going to run the Pi in text only mode or headless, you can run the following command:

```bash
sudo raspi-config
```

 - Select option 8 : `Advanced Options`, `Memory Split`
 - Give the GPU (Graphics Processor) the least amount of memory (16).

This will give the lion's share of the memory to the core functions.
