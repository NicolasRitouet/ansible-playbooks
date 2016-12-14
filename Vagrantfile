# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"

  config.ssh.insert_key = false

  config.vm.define "localhost" do |l|
    l.vm.hostname = "localhost"
  end

  config.vm.provider :virtualbox do |vb|
    vb.name = "ubuntu-xenial"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = "playbooks/main.yml"
    ansible.verbose = "v"
    ansible.host_key_checking = false
  end
end