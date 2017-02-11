# -*- mode: ruby -*-
# vi: set ft=ruby :
# Author: andrei@skopenko.net

load 'Vagrantfile.local' if File.exist?('Vagrantfile.local')

hostname = 'vagrant-ansible-centos7.dev'

Vagrant.configure('2') do |config|
  config.vm.hostname = hostname

  config.vm.provider :parallels do |v, override|
    v.name = hostname
    v.memory = 2048
    v.cpus = 1
    override.vm.box = 'bento/centos-7.2'
    override.vm.synced_folder '~', '/opt/Home', mount_options: ['share']
    override.vm.synced_folder './src', '/opt/src', mount_options: ['share']
  end

  config.vm.provider :virtualbox do |v, override|
    v.name = hostname
    v.memory = 1024
    v.cpus = 2
    override.vm.box = 'chef/centos-7.2'
    override.vm.synced_folder '~', '/opt/Home'
    override.vm.synced_folder './src', '/opt/src'
  end

  config.vm.provision :ansible_local do |ansible|
    ansible.install = true
    ansible.version = "latest"
    ansible.sudo = true
    #ansible.verbose = 'v'
    ansible.playbook = 'ansible/playbook.yml'
    ansible.galaxy_role_file = 'ansible/requirements.yml'
  end
end
