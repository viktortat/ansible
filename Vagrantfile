# -*- mode: ruby -*-
# vi: set ft=ruby :

hosts = {
  "raz1" => "192.168.53.21",
#  "web2" => "192.168.33.22",
#  "web3" => "192.168.33.23"
}

Vagrant.configure("2") do |config|
    hosts.each do |name, ip|
        config.vm.define name do |machine|
            machine.vm.box = "debian/jessie64"
            machine.vm.hostname = "%s.example.org" % name
            machine.vm.network :private_network, ip: ip
            machine.vm.provider "virtualbox" do |v|
                v.name = name
                v.customize ["modifyvm", :id, "--memory", 800]
            end
        end
    end
end
