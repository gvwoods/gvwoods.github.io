---
id: 10
title: Determine what Linux Version
date: 2017-12-20T15:12:00-05:00
author: George Woods
layout: post
permalink: /2017/12/20/determine-what-linux-version/
blogger_blog:
  - gvwoods.blogspot.com
blogger_author:
  - George Woods
blogger_permalink:
  - /2017/12/determine-what-linux-version.html
blogger_internal:
  - /feeds/27386963/posts/default/3299549005424335552
categories:
  - Linux
---
4 different commands that you can run to see information about your Linux distro.

**[oracle@server ~]$ cat /etc/issue**  
<span style="color: #3d85c6;">Oracle Linux Server release 6.8</span>

**[oracle@server ~]$ cat /etc/*release**  
<span style="color: #3d85c6;">LSB_VERSION=base-4.0-amd64:base-4.0-noarch:core-4.0-amd64:core-4.0-noarch:graphics-4.0-amd64:graphics-4.0-noarch:printing-4.0-amd64:printing-4.0-noarch</span>  
<span style="color: #3d85c6;">Oracle Linux Server release 6.8</span>  
<span style="color: #3d85c6;">NAME=&#8221;Oracle Linux Server&#8221;</span>  
<span style="color: #3d85c6;">VERSION=&#8221;6.8&#8243;</span>  
<span style="color: #3d85c6;">ID=&#8221;ol&#8221;</span>  
<span style="color: #3d85c6;">VERSION_ID=&#8221;6.8&#8243;</span>  
<span style="color: #3d85c6;">PRETTY_NAME=&#8221;Oracle Linux Server 6.8&#8243;</span>  
<span style="color: #3d85c6;">ANSI_COLOR=&#8221;0;31&#8243;</span>  
<span style="color: #3d85c6;">CPE_NAME=&#8221;cpe:/o:oracle:linux:6:8:server&#8221;</span>  
<span style="color: #3d85c6;">HOME_URL=&#8221;https://linux.oracle.com/&#8221;</span>  
<span style="color: #3d85c6;">BUG_REPORT_URL=&#8221;https://bugzilla.oracle.com/&#8221;</span>  
<span style="color: #3d85c6;"><br /></span><span style="color: #3d85c6;">ORACLE_BUGZILLA_PRODUCT=&#8221;Oracle Linux 6&#8243;</span>  
<span style="color: #3d85c6;">ORACLE_BUGZILLA_PRODUCT_VERSION=6.8</span>  
<span style="color: #3d85c6;">ORACLE_SUPPORT_PRODUCT=&#8221;Oracle Linux&#8221;</span>  
<span style="color: #3d85c6;">ORACLE_SUPPORT_PRODUCT_VERSION=6.8</span>  
<span style="color: #3d85c6;">Red Hat Enterprise Linux Server release 6.8 (Santiago)</span>  
<span style="color: #3d85c6;">Oracle Linux Server release 6.8</span>

**<u>Kernel Version commands</u>**  
**[oracle@server ~]$ uname -r**  
<span style="color: #3d85c6;">4.1.12-103.9.6.el6uek.x86_64</span>

**Whether you are using 32 bit or 64 bit version&#8230; the x86_64 means a 64 bit kernel

**[oracle@server ~]$ uname -a**  
<span style="color: #3d85c6;">Linux server 4.1.12-103.9.6.el6uek.x86_64 #2 SMP Wed Nov 15 18:03:27 PST 2017 x86_64 x86_64 x86_64 GNU/Linux</span>