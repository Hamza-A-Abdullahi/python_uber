# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
  Vagrant.configure("2") do |config|
    config.vm.define "python" do |python|
      python.vm.box = "ubuntu/xenial64"
      python.vm.network "private_network", ip: "192.168.10.100"
      python.hostsupdater.aliases = ["development.local"]
      python.vm.synced_folder "Python-Sample-Application", "/home/ubuntu/Python-Sample-Application"


      python.vm.provision "chef_solo" do |chef|
        chef.arguments = "--chef-license accept"
        chef.add_recipe "python::default"
      end
    end
end
