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
	end
end
