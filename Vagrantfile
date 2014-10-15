# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder "./data", "/vagrant_data", :mount_options => ['dmode=775', 'fmode=664']
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "./ansible.yml"
    ansible.inventory_path = "./ansible_host"
    ansible.limit = 'all'
  end
  
end
