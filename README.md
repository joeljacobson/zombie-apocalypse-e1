#Zombie Apocalypse

VM for Zombie Apocalypse episode one.

##Prerequisites

Make sure all of these are installed and up-to-date.

* [Virtualbox](https://www.virtualbox.org/)
* [Vagrant](https://www.vagrantup.com/downloads.html)
* [Ansible](http://docs.ansible.com/intro_installation.html)

##Provisioning

Clone the project: `git clone https://github.com/joeljacobson/zombie-apocalypse-e1.git`

In the project directory enter: `vagrant up`

Your DataStax node will be ready shortly depending on your internet connection. The initial boot takes some time as Ansible has to download, install and configure DataStax Enterprise. Subsequent reboots are fast. If you experience any errors, destroy and recreate the vm.

When successful, halt the VM ready for the exercises `vagrant halt`

---

#Episode One

Instructions included with slides.
