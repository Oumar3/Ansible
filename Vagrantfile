# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.


Vagrant.configure("2") do |config|

  config.vm.define "ansiblehoste" do |ansible|
    ansible.vm.box = "bento/ubuntu-20.04"
    ansible.vm.network "private_network", ip:"192.168.33.10"
    ansible.vm.synced_folder "./ansible", "/vagrantAnsible"
    ansible.vm.hostname = "ansible-config"

    
    ansible.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
      vb.name = "ansible-config"
      vb.gui = false
    end
  end


  config.vm.define "node1" do |node1|
    node1.vm.box = "bento/ubuntu-22.04"
    node1.vm.network "private_network", ip:"192.168.33.11"
    node1.vm.hostname = "ansible-client-web"
  
    node1.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
      vb.gui = false
      vb.name = "ansible-client-web"
    end
  end

  config.vm.define "node2" do |node2|
    node2.vm.box = "bento/ubuntu-22.04"
    node2.vm.hostname = "ansible-client-db" 
    node2.vm.network "private_network", ip:"192.168.33.12"

    node2.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.name = "ansible-client-db"
      vb.gui = false
      vb.cpus = 2
    end
  end

end

