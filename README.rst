ansible-midpoint
================

Vagrant and Ansible setup for Midpoint

Prerequisites
--------------
Vagrant
VirtualBox
Python
python-simplejson
Ansible

Setup
------

1. ::

	git clone http://github.com:edthedev/ansible-midpoint.git
	mkdir midpoint/sources

2. Download Midpoint binaries into the sources directory. Ensure it is named `midpoint-2.2.1-dist.zip`, or update playbook.yml to match the new name.

3. ::

	cd midpoint
	vagrant up
	curl localhost:8080

Then visit localhost:8080 in Firefox.

Tomcat Notes
-------------
Tomcat Service Config: /etc/tomcat6 (main config directory)
Release Notes        : ﻿/usr/share/doc/tomcat*
Bin Directory        : /usr/share/tomcat6
Webapps              : /var/lib/tomcat6/webapps
Logs                 : /var/log/tomcat6
