# dev-node
Development environment using vagrant+ansible: git, java, nodejs...

## Requirements
You need:

* [VirtualBox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/)

## Install

```
vagrant up
vagrant ssh
```

## Configure
You can choose between different playbooks:

* nodejs: install git, nodejs
* mobile: install git, java, nodejs, cordova and android sdk

You can edit playbook variables, for example choose nodejs version:

```
- { role: "nodejs", nodejs_version: '6.x'}
```

And of course, you can make your own playbook or add roles.

## Ansible roles
In install_roles.yml you can view and edit the source of roles and install/uninstall them:

```
cd /vagrant/roles
ansible-galaxy install -r install_roles.yml -p . --force
ansible-galaxy remove -r install_roles.yml
```
