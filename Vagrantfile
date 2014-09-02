unless Vagrant.has_plugin?("berkshelf")
  raise 'vagrant-berkshelf is not installed, use "vagrant plugin install vagrant-berkshelf" to install it'
end

# Depends on installed precise64
# "vagrant box add precise64 http://files.vagrantup.com/precise64.box""
# Or try on trusty64 "vagrant box add ubuntu/trusty64"
Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  #config.vm.box = "ubuntu/trusty64"
  config.vm.provider "virtualbox" do |v|
    v.memory = 512
    v.cpus = 1
  end
  config.berkshelf.enabled = true
  # Allow installation of newer Rubies (AWS uses 2.0.0 now) and update
  # Chef if needed.  On Trusty update-alternatives does not work for
  # ruby, so we symlink manually.
  config.vm.provision :shell, :inline => 'if [[ `chef --version` != *11.10.* ]]; then apt-get update;  apt-get install python-software-properties --no-upgrade --yes; add-apt-repository ppa:brightbox/ruby-ng-experimental; apt-get update; apt-get install build-essential bash-completion ruby2.0 ruby2.0-dev --yes; update-alternatives --set ruby /usr/bin/ruby2.0 || ln -sf /usr/bin/ruby2.0 /usr/bin/ruby; update-alternatives --set gem /usr/bin/gem2.0 || ln -sf /usr/bin/gem2.0 /usr/bin/gem; gem install chef --version 11.10.4 --no-rdoc --no-ri --conservative; fi'
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "."
    chef.add_recipe("plone_buildout::example")
    chef.json = {}
  end
  config.vm.network :forwarded_port, guest: 80, host: 12080
  config.vm.network :forwarded_port, guest: 8081, host: 12081
end
