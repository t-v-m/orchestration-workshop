# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"
  
  config.ssh.forward_agent = true
  
  config.vm.define "provisioner" do |provisioner|
	config.vm.provider :virtualbox do |vb|
        vb.name = "provisioner"
    end
	provisioner.vm.hostname = "provisioner"
	provisioner.vm.network "forwarded_port", guest: 80, host: 8888
	provisioner.vm.network "private_network", ip: "192.168.10.21"
  end
  
  config.vm.define "balancer" do |balancer|
	config.vm.provider :virtualbox do |vb|
        vb.name = "balancer"
    end
	balancer.vm.hostname = "balancer"
	balancer.vm.network "forwarded_port", guest: 80, host: 8000
	balancer.vm.network "private_network", ip: "192.168.10.22"
  end
  
  config.vm.define "webServer1" do |webServer1|
	config.vm.provider :virtualbox do |vb|
        vb.name = "webServer1"
    end
    webServer1.vm.hostname = "web-server-1"
	webServer1.vm.network "private_network", ip: "192.168.10.23"
  end
  
  config.vm.define "webServer2" do |webServer2|
	config.vm.provider :virtualbox do |vb|
        vb.name = "webServer2"
    end
    webServer2.vm.hostname = "web-server-2"
	webServer2.vm.network "private_network", ip: "192.168.10.24"
  end
  
  config.vm.define "database" do |database|
	config.vm.provider :virtualbox do |vb|
        vb.name = "database"
    end
    database.vm.hostname = "database"
	database.vm.network "forwarded_port", guest: 80, host: 8885
	database.vm.network "private_network", ip: "192.168.10.25"
  end
  
end
