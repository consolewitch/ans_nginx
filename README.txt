Warnings:
=========

1) This playbook will disable the IPTables firewall.
2) Running this playbook will temporairly stop your NginX server.
3) Other NginX sites running on this server will be disabled. (see notes)


Variables:
==========
gitRepo		: URL of a Git repo containing html to serve.
portNumber	: Port upon which to serve the repo.


As the script completes it will give you the address where you can access 
the new web server.


Notes:
======
If you run this script against a server that is already serving
nginx files, it will disable all your other sites in favor of its
own. If this happens accidentally it is easy to fix, simply 
create symbolic links from /etc/nginx/conf.available/site.conf to
/etc/nginx/conf.d

This playbook is designed for Centos 6.x. Centos 7 introduced
systemd and some other technologies that may not be compatible.
It will not run on Ubuntu and has not been tested on any other
Linux distribution.

-=-
2015/06/16
alex@speaks.io
    


