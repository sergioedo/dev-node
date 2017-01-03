# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.synced_folder "c:/src", "/src"

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "1024"
    vb.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
  end

  # config.vm.provision :shell, :inline => "echo \"America/New_York\" | sudo tee /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata"
  # http://unix.stackexchange.com/questions/110522/timezone-setting-in-linux
  # http://manpages.ubuntu.com/manpages/jaunty/man3/DateTime::TimeZone::Catalog.3pm.html
  config.vm.provision :shell, :inline => "echo \"Europe/Madrid\" | sudo tee /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata"

end
