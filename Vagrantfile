# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.box = "geerlingguy/ubuntu1604"
    config.vm.box_url = "https://vagrantcloud.com/geerlingguy/boxes/ubuntu1604"
    config.vm.define "node" do |node|
      node.vm.hostname = "node"
      node.vm.network "private_network", ip: "192.168.56.10"
      config.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--memory", "4096"]
        vb.cpus = 2
          config.vm.provision :ansible do |ansible|
            ansible.limit = "all"
            ansible.playbook = "site.yml"
          end
        end
      end
    end
