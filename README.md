## Auto-Web

AutoWeb is an un-complicated Debian-based web interface.

Its goal is to provide a simple admin interface for anyone that would like to self-host multiple websites as subdomains under the same top-level domain.

it is primarily intended as a "hosted-by-friend" mass VirtualHost hosting, and can be used by web teachers to setup in a snap multiple web folders to students.

AutoWeb is written with PHP and Ansible and can power PHP+MySQL web environments.

## Features

 - Automatic configuration of web services: MySQL, Apache, Bind9, PHP
 - Mass import of web accounts
 - Provides a chrooted shell to allow users to run commands inside their web folders
 - Multiple admins can be configured to access database and files of all users
 - Supports Linux file quotas
 - LetsEncrypt support (soon)

## Limitations

The users passwords are actually stored in plain text in the software database, to make it easier to give it back to users in case of password lost. This may change in future releases.