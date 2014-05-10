# -*- mode: ruby -*-
# vi: set ft=ruby :

project_name = 'android-dev'
ip_address   = '192.168.65.10'
chef_version = '11.12.0'
base_box     = 'ubuntu-13.04-vanilla'
base_box_url = 'http://goo.gl/KwQSa2'
hostname     = "#{project_name}.local.bschlueter.com"

Vagrant.configure("2") do |config|
  config.omnibus.chef_version = chef_version
  config.vm.box               = base_box
  config.vm.box_url           = base_box_url

  config.vm.provider :virtualbox do |vb|
    vb.name = project_name
  end

  config.vm.network :private_network, ip: ip_address
  config.vm.synced_folder(
    '..',
    "/home/vagrant/workspaces/#{project_name}",
    :owner => 'vagrant',
    :mount_options => ['dmode=775']
  )
  config.vm.hostname = hostname

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = %w{ kitchen/cookbooks kitchen/site-cookbooks }
    chef.roles_path     = 'kitchen/roles'
    chef.data_bags_path = 'kitchen/data_bags'

    chef.custom_config_path = 'kitchen/ssl_fix.chef'

    chef.add_role project_name
  end
end
