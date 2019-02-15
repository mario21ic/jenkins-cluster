# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|

    config.vm.define "master", primary: true do |node|
        node.vm.box = "ubuntu/xenial64"
        node.vm.hostname = "master"
        node.vm.network "private_network", ip: "192.168.2.10"
        node.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
            vb.cpus = 2
        end
        node.vm.provision "shell", inline: "sudo apt-get install -y python"
        node.vm.provision :ansible do |ansible|
            ansible.playbook = "./playbook.master.yml"
        end
    end

    config.vm.define "worker1" do |node|
        node.vm.box = "ubuntu/xenial64"
        node.vm.hostname = "worker1"
        node.vm.network "private_network", ip: "192.168.2.11"
        node.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
            vb.cpus = 2
        end
        node.vm.provision "shell", inline: "sudo apt-get install -y python"
        node.vm.provision :ansible do |ansible|
            ansible.playbook = "./playbook.slave.yml"
        end
    end

    config.vm.define "worker2" do |node|
        node.vm.box = "ubuntu/xenial64"
        node.vm.hostname = "worker2"
        node.vm.network "private_network", ip: "192.168.2.12"
        node.vm.provider "virtualbox" do |vb|
            vb.memory = "2048"
            vb.cpus = 2
        end
        node.vm.provision "shell", inline: "sudo apt-get install -y python"
        node.vm.provision :ansible do |ansible|
            ansible.playbook = "./playbook.slave.yml"
        end
    end

end
