# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
  end

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.install = true
    ansible.galaxy_role_file = "requirements.yml"
    ansible.galaxy_roles_path = "roles"
    ansible.extra_vars = "vars.yml"
  end

end