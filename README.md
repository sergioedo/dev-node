# dev-node
Development environment using vagrant+ansible: git, java, nodejs...

## Requirements
You need:

* VirtualBox
* Vagrant

## Install

'
vagrant up
vagrant ssh
'

## Configure
You can choose between different playbooks:

* nodejs: install git, nodejs
* mobile: install git, nodejs, cordova and android sdk

You can edit playbook variables, for example choose nodejs version:

'
...

'

And of course, you can make your own playbook or add roles.

## Ansible roles
In install_roles.yml you can view and edit the source of roles and install/uninstall them:

'
cd /vagrant/roles
ansible-galaxy install -r install_roles.yml -p . --force
ansible-galaxy remove -r install_roles.yml
'