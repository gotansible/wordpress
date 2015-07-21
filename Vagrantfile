# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANT_VERSION = 2
Vagrant.configure(VAGRANT_VERSION) do |config|
	config.vm.define "wordpress" do |server|
		server.vm.box = "phusion/ubuntu-14.04-amd64"
		server.vm.hostname = "wordpress"
		server.vm.provision :ansible do |ansible|
			ansible.playbook = "test.yml"
		end
		server.vm.network "private_network", ip: "192.168.50.10"
		server.vm.network "forwarded_port", guest: 80, host: 9999
	end

	config.vm.define "mariadb" do |server|
		server.vm.box = "phusion/ubuntu-14.04-amd64"
		server.vm.hostname = "mariadb"
		server.vm.provision :ansible do |ansible|
			ansible.playbook = "test-mariadb.yml"
		end
		server.vm.network "private_network", ip: "192.168.50.200"
	end

end
