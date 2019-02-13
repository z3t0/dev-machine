# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/arch"

  # Python is needed for ansible
  config.vm.provision "shell", inline: <<-SHELL
	pacman -S python --noconfirm
  SHELL

  config.vm.provision :ansible do |ansible|
	  ansible.playbook = "playbook.yml"
  end
end
