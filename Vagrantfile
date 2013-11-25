# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos64"
  config.vm.box_url = "http://packages.vstone.eu/vagrant-boxes/centos-6.x-64bit-latest.box"

  config.vm.network :private_network, ip: "192.168.101.111"
  
  config.vm.synced_folder "www", "/var/www/html"
  #config.vm.synced_folder "bats/bin", "/home/vagrant/bin"
  #config.vm.synced_folder "bats/libexec", "/home/vagrant/libexec"
  #config.vm.synced_folder "bats/tests", "/home/vagrant/tests"

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file  = "site.pp"
    puppet.module_path = "modules"
  end
end
