# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "chef/centos-6.5"
  # config.vm.box_check_update = false
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "private_network", ip: "192.168.33.222"
  # config.vm.network "public_network"
  # config.ssh.forward_agent = true
  config.ssh.pty = true
  config.vm.synced_folder "./data", "/vagrant", create: true


  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "./provisioning/init.yml"
    ansible.inventory_path = "./provisioning/hosts"
    ansible.sudo = true
    ansible.limit = "all"
    ansible.verbose = "vvv"
 end

end
