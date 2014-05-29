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

2. Download Midpoint binaries into the sources directory.
 
   Unzip the file to `sources/midpoint-2.2.1/`.
   If necessary, update the `midpoint_war variable` in `playbook.yml`. 

3. ::

	cd midpoint
	vagrant up
	curl localhost:8080

4. Configure Tomcat::

   vagrant ssh 
   vim /usr/share/tomcat6/catalina.sh
   sudo vi /etc/tomcat6/tomcat6.conf

Edit catalina.sh:: 

   ...
   JAVA_OPTS="$JAVA_OPTS -Dmidpoint.home=/opt/midpoint"
   ...

5. Restart Tomcat::

   sudo service tomcat6 restart

6. Enjoy the Tomcat log file.::

   vi /var/log/tomcat6/catalina.out

7. Visit MidPoint Admin on localhost_admin_ site in Firefox.

.. _localhost_admin: http://localhost:8080/midpoint/admin/

Tomcat Notes
-------------
Tomcat Service Config: /etc/tomcat6 (main config directory)
Release Notes        : /usr/share/doc/tomcat*
Bin Directory        : /usr/share/tomcat6
Webapps              : /var/lib/tomcat6/webapps
Logs                 : /var/log/tomcat6
