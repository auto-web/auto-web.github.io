# Update AutoWeb

1. Make sure you have a backup of the folder `/opt/autoweb` and all your user data, including SQL databases.
2. Simply pull the new code from the repository in `/opt/autoweb`.
3. Run the install playbook again: `ansible-playbook /opt/autoweb/robot/install.yml`
4. Run the additionnal MySQL schema changes located in `/opt/autoweb/interface/lib/`
5. If needed, update the Jailkit jail: `jk_update -j /data/chroot/ && jk_init -j /data/chroot/ autoweb`