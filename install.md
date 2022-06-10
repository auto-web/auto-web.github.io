# Installing AutoWeb

## Requirements

Be sure to read the [requirements](/requirements) hints before beginning.

Setup a blank Debian server with appropriate partitions.

## Initial Setup

1. Log into your server
2. Install the following packages: `git` `python` `python3` `python3-pip`  `mariadb-server` `mariadb-client` `quota` `quotatool`
3. Install Ansible from PIP: `pip3 install ansible pymysql`
4. Secure the MySQL installation with the command `mysql_secure_installation`
5. Edit `/etc/fstab` to add the following to the `/data` partition options (after the defaults `defaults` keyword): `defaults,usrjquota=quota.user,grpjquota=quota.group,jqfmt=vfsv0`
6. Remount and enable quotas: `mount -o remount /data && quotaon -a`
7. Create Ansible MySQL user: 
   1. Login to MySQL prompt as root
   2. Run `CREATE USER ansible@localhost IDENTIFIED BY '...';` make sure to replace `...`with a password.
   3. Run `GRANT ALL PRIVILEGES ON *.* TO 'ansible'@'localhost' WITH GRANT OPTION;`

## Installation of AutoWeb robot

1. Clone the repository to `/opt`, you should end up with a folder named `/opt/autoweb` containing two folders : `interfaces` et `robot`.
2. Copy `/opt/autoweb/robot/data-exemple` to `/opt/autoweb/robot/data` and edit the file according to your needs. The file is commented to help you change the values accordingly.
3. Finally, install the software by running the playbook: `ansible-playbook /opt/autoweb/robot/install.yml`


## Setup of AutoWeb interface

The initial AutoWeb interface setup is not (yet) automated.

In order to create the initla tables and admin user, execute the two SQL files located in `/opt/autoweb/interface/lib`.

You can now lo into your web interface with the login `admin` and the password `admin`.


## Troubleshooting

If The installation looks stuck with Jailkit configuration, install it manually: https://olivier.sessink.nl/jailkit/

