---
id: 155
title: Using alias to upgrade old servers
date: 2018-02-07T01:12:37-05:00
author: gvwoods75
layout: post
guid: http://georgevwoods.com/?p=155
permalink: /2018/02/07/using-alias-to-upgrade-old-servers/
image: /wp-content/uploads/2018/02/win2000advserv.png
categories:
  - DBA
---
One trick that I have used numerous times and really like is to use a server alias when moving to new servers. For instance, we were moving numerous databases from a 2000 server named serversql0001. Since this server was so old, we had no real idea how many places or connections people may have used the alias, so we decided during the downtime to remove this alias and point it to the new server that we were moving the databases to. After we brought the new server up, we checked some of the software that was connecting to the databases, and as expected, everything was fine, with no need for connection changes.