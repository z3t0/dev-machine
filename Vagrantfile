# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/arch"

  # Network
  config.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"

  # Virtual box
  config.vm.provider "virtualbox" do |v|
	  v.memory = 4096
	  v.cpus = 2
  end

  # Python is needed for ansible
  config.vm.provision "shell", inline: <<-SHELL
	pacman -S python --noconfirm --needed
  SHELL

  # Ansible provisioning
  config.vm.provision :ansible do |ansible|
	  ansible.playbook = "provisioning/playbook.yml"
  end
end
