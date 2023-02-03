[DOCUMENTATION on wiki](https://github.com/DevelopersPL/otshosting-provisioning/wiki)

otshosting-provisioning
=======================
This is an Ansible playbook used to fully provision a Ubuntu machine for OTS Hosting.

__Supported OS: Ubuntu 20.04__

Make sure to have universe, multiverse and restricted repositories enabled.

A script to run on a standalone machine to provision it. If user "otsmanager" does not exist, it will be created with password: "otsmanager". MAKE SURE TO CHANGE THE PASSWORD
```bash
#!/bin/bash -ex
apt-get update
apt install -y -q python-simplejson git-core ansible
ansible-pull -i localhost, -U https://github.com/ImmortalDisorderOT/otshosting-ansible.git -d /srv/otshosting-provisioning --purge -t default
```

Available tags:

* systemd - enables persistent journald logging (default)
* general - software & integration (default)
* mysql - MariaDB SQL server (default)
* php-fpm - PHP support for website (default)
* nginx - web server (default)
* tfs - TFS 1.X automatically compiled and installed (default)
* tfsaac - ID-ZnoteAAC automatically installed & configured (default)



