# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  # https://docs.vagrantup.com.
  config.vm.box = 'bento/ubuntu-18.04'
  config.vm.hostname = 'tdocker01'
  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # no net config avail with hyper-v :(
  # config.vm.network "Public_vSwitch"

  config.vm.synced_folder 'C:/Users/mplex/Documents/projects', '/code'

  config.vm.provider 'hyperv' do |hv|
    hv.cpus         = '2'
    hv.memory       = '4096'
    hv.linked_clone = true
  end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision 'shell', inline: <<-SHELL
    apt-get update
    apt-get upgrade -y
    pip3 install ansible
  SHELL

  # doesn't work with windows
  # run ansible after
  # might be able to run from ubuntu shell on windows, using remote hyper-v
  # config.vm.provision 'ansible' do |ansible|
  #   ansible.playbook = 'docker.yml'
  # end
end
