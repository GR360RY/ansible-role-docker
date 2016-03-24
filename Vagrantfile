# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provider "virtualbox" do |vb|
    vb.linked_clone = true if Vagrant::VERSION =~ /^1.8/
  end

  if File.exist?("../ansible-role-docker") then
    config.vm.provision :ansible do |ansible|
    	ansible.playbook = "tests/github_role_playbook.yml"
  	end
  end

  if File.exist?("../GR360RY.docker") then
    config.vm.provision :ansible do |ansible|
    	ansible.playbook = "tests/galaxy_role_playbook.yml"
  	end
  end

end
