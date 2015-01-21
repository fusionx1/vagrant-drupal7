Vagrant::Config.run do |config|
  config.vm.box = "vagrant-drupal3"
  #config.vm.box_url = "http://files.vagrantup.com/lucid32.box"

  config.vm.customize ["modifyvm", :id, "--memory", "2048"]

  config.vm.network :hostonly, "192.168.33.20"

  # Change to preferred file location.
  # config.vm.share_folder("web", "/var/www", "web")
    config.vm.share_folder "web", "/var/www", "web", :mount_options => ["dmode=777","fmode=777"]
  # config.vm.share_folder("web", "/var/www", "web", :owner=> 'vagrant', :group=>'httpd', :extra => 'dmode=777,fmode=777')
    config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file = "default.pp"
    puppet.module_path = "modules"
  end
end
