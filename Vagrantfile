# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos7"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provider :virtualbox do |v|
    v.memory = 8192
    v.linked_clone = true
  end  

  # App server 1
  config.vm.define "apigee" do |app|
    app.vm.network :private_network, ip:"192.168.60.4"
    app.vm.network "forwarded_port", guest: 9000, host: 9000
    app.vm.network "forwarded_port", guest: 8080, host: 8080
  end
end
