---
layout: post
title: "Chef Server Not Surviving Reboot on Ubuntu 12.04"
date: 2012-12-14 09:54
comments: true
categories:
---
I was setting up a new Chef server on Ubuntu 12.04 and for some reason the Chef Server
and Chef Web UI wouldn't automatically start on (re)boot. I found the solution here:

http://tickets.opscode.com/browse/CHEF-3204

In case that link dries up, here's the short answer:

First:
<pre>
sudo update-rc.d -f couchdb remove
sudo update-rc.d -f rabbitmq-server remove
sudo update-rc.d -f chef-solr remove
sudo update-rc.d -f chef-expander remove
sudo update-rc.d -f chef-server remove
sudo update-rc.d -f chef-server-webui remove
</pre>

Then:
<pre>
# the dots are required
sudo update-rc.d couchdb start 20 2 3 4 5 . stop 22 0 1 6 .
sudo update-rc.d rabbitmq-server start 20 2 3 4 5 . stop 22 0 1 6 .
sudo update-rc.d chef-solr start 20 2 3 4 5 . stop 22 0 1 6 .
sudo update-rc.d chef-expander start 21 2 3 4 5 . stop 21 0 1 6 .
sudo update-rc.d chef-server start 21 2 3 4 5 . stop 21 0 1 6 .
sudo update-rc.d chef-server-webui start 22 2 3 4 5 . stop 20 0 1 6 .
</pre>
