# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "public_network", use_dhcp_assigned_default_route: true, bridge: "en4: AX88179 USB 3.0 to Gigabit Ethernet"
  config.vm.provider "virtualbox" do |vb|
    vb.linked_clone = true if Vagrant::VERSION =~ /^1.8/
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "docker.yml"
  end

end
