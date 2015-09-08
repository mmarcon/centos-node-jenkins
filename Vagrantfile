# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "puphpet/centos65-x64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  # No need to sync the vagrant folder, everything gets deployed
  # with the ansible playbook
  config.vm.synced_folder '.', '/vagrant', :disabled => true

  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = false
    vb.memory = "512"
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
