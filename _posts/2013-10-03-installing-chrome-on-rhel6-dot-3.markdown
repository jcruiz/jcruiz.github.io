---
# layout: post
title: "Installing Chrome on RHEL6.3"
date: 2013-10-03 00:04
comments: true
categories: [techonology, installation, enterprise]
---

Facing an interesting task the other day at work. Install [Google Chrome](https://www.google.com/intl/en/chrome/browser/) in a RHEL6.3 machine. This seems like a pretty standard task to be performed.

Interesting enough, Google is not longer supporting RedHat-based linux flavours such as CentOS or Fedora. This to me is actually shocking at the same time that completely puts my engineering ego in the spot.
<!--more-->
After googling around for hours I managed to get it working. Thank to [Richar Lloyd](http://chrome.richardlloyd.org.uk/) and [Narad Shrestha](http://www.tecmint.com/install-google-chrome-on-redhat-centos-fedora-linux/), I was able to see the light at the end of the tunnel.

So follow up the above link from Naradm, then it will prompt you to upgrade the entire system to a new version in order to run chrome, which really is ridiculous - instead just upgrade nss by doing:

``yum update nss``

after that you will be able to execute google-chrome as a non-root user.

Also as a recommendation, enter your RHN credential directly during installation, as this is the only way to get YUM up and running without a problem. Otherwise you will get stuck trying to run commands in the terminal + searching for the right wizard that allows you to register you machine into the RHN.

Mission accomplished
