# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

MEMORY = 1024   # leave 4GiB for the host
CPUS = 1        # max 2

required_plugins = %w(vagrant-hostmanager)

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  
  # config.vm.synced_folder ".", "/vagrant", disabled: true
  # config.vm.synced_folder ".", "/vagrant", disabled: true
  
  config.vm.network :private_network, ip: "192.168.56.101"
  config.vm.network "forwarded_port", guest: 8080, host: 8180

  config.vm.provider "virtualbox" do |virtualbox|
    virtualbox.cpus = CPUS
    
    virtualbox.memory = MEMORY

    # Don't boot with headless mode
    virtualbox.gui = true
  end

  # config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
  config.vm.provision "fix-no-tty", type: "shell" do |s|
    s.privileged = true
    s.inline = "sudo sed -i '/tty/!s/mesg n/tty -s \\&\\& mesg n/' /root/.profile"
  end
  config.vm.provision "shell", path: "scripts/install-jenkins.sh"

end
