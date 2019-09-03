# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network "forwarded_port", guest: 3011, host: 3011
  config.vm.network "forwarded_port", guest: 3033, host: 3033
  config.vm.network "forwarded_port", guest: 3035, host: 3035
  config.vm.network "forwarded_port", guest: 3100, host: 3100
  config.vm.network "forwarded_port", guest: 5000, host: 5000
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end
  config.ssh.forward_agent = true
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.galaxy_role_file = "provisioning/requirements.yml"
  end
end
