# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/7"
  config.vm.network :private_network, ip: "192.168.1.3"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory = 1500
    v.cpus = 2
    #v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
  end

  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become = true
  end
end
