# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "lde/nomad"
  config.vm.host_name = "nomad"
  config.vm.post_up_message = "Have a nice day :)"
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end
  config.vm.network "forwarded_port", guest: 4646, host: 4646, host_ip: "127.0.0.1"
  config.vm.network "forwarded_port", guest: 8500, host: 8500, host_ip: "127.0.0.1"
  config.vm.provider "virtualbox" do |v|
    v.memory = "4096"
    v.cpus = 4
    v.name = "Nomad"
  end
end
