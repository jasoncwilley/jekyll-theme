---
layout: post
title: "How to install virtualenv on ArchLinux"
description: "Installing virtualenv and it's dependencies on ArchLinux."
tags: [python, pip, virturalenv, archlinux, install, guide, step by step, tutorial]
comments: true
share:  true
image:
  background: cube.png
---
##Python and ArchLinux

ArchLinux may not be the most user friendly Linux OS and in my opinion that is by design.  Simply installing ArchLinux is a feat for the novice linux user.  Once installed users must configure the system and I'd be willing to bet that the majority of those new to Arch never make it through the configuration phase post install.  Over the years I have played around with Archlinux and after spending hours digging through the docs, Archwiki, and watching countless Youtube videos a lightbulb went off and all the puzzle pieces began to fit together.  If you have not had a chance to check out my ArchLinux install tutorial please take a minute to check it out.

ArchLinux is unique in the way it handles Python and comes with Python3.6 pre-installed.  To check and make sure your system has a working version of Python open up a termnal window and type python then hit return.  If you have Python installed you will see somehting like the following.

```
[minty@minty ~]$ python
Python 3.6.4 (default, Jan  5 2018, 02:35:40)
[GCC 7.2.1 20171224] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
As you can see the results show that my system has python3.6 installed as the default version.

This is all fine and dandy if I am working on coding projects that use only Python3, but what if I would like to code a project or load a project that requires Python2 dependencies.

Here is where virutalenv comes into play.  Virtualenv solves this problem marvelously.  It is a sandbox that allows you to manage your project’s library in whichever versionof Python you chose.

Before we install virutalenv let's make sure we have all the software we will need to complete this tutorial and install virtualenv.

##Dependencies Needed to Complete this Tutorial

* sudo
* python-setuptools
* pyton-pip
* python2 (If you don't have both Python2 installed see my post on installing it before you proceed)

Most of you probably have already installed and configured sudo.  Sudo can be installed via the pacman command and the configuration file can be found here /etc/sudoers.

```
[root@minty minty]# pacman -S sudo
```

Note:  You must be the root user to install sudo via pacman

Once you have sudo installed and added your username to the sudoers configuration file you can now use sudo to invoke root privilages.

Now let's move on and install both the setuptools and pip using the sudo command.

```
[minty@minty ~]$ sudo pacman -S python-setuptools python-pip
```

If all goes well and you do not recieve any errors you should have everything you need to install Virtualenv

##Installing Virtualenv via pip

Installing virtualenv is quite easy using pip and can be accomplished by simply entering the following command into the terminal.

```
[minty@minty ~]$ sudo pip install virtualenv
```

{% if page.comments %}
<div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = '//jajb.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}




