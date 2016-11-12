# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.define 'dev' do |c|
    c.vm.box = 'ubuntu/xenial64'
    c.vm.network :private_network, ip: '192.168.88.27'
    c.vm.hostname = 'ubuntu-xenial'
    c.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'playbook.yml'
      ansible.sudo = true
      ansible.host_key_checking = false
    end
  end
end