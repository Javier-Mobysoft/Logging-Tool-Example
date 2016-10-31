# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "phusion/ubuntu-14.04-amd64"


  # fix "stdin: is not a tty" error
  config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

  config.vm.define "support" do |support|
    support.vm.provider "virtualbox" do |vb|
      # Customize the amount of memory on the VM:
      vb.memory = "3072"
      vb.cpus = 2
    end

    support.vm.network "private_network", ip: "192.168.33.100"

    support.vm.provision :docker
    support.vm.provision :docker_compose, yml: "/vagrant/docker.yml"

  end



end
