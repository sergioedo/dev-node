# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "dev"
  # Disable VBGuestAdditions update (faster creation)
  # config.vbguest.auto_update = false

  #Accessible ports:
  config.vm.network "forwarded_port", guest: 8000, host: 8000

  config.vm.synced_folder "c:/src", "/src"

  config.vm.provider "virtualbox" do |vb|
    # Customize the amount of memory on the VM:
    vb.memory = "2048"
    vb.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
  end

  # config.vm.provision :shell, :inline => "echo \"America/New_York\" | sudo tee /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata"
  # http://unix.stackexchange.com/questions/110522/timezone-setting-in-linux
  # http://manpages.ubuntu.com/manpages/jaunty/man3/DateTime::TimeZone::Catalog.3pm.html
  config.vm.provision :shell, :inline => "echo \"Europe/Madrid\" | sudo tee /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata"
  
  # Run Ansible from the Vagrant VM
  #config.vm.provision "ansible_local", run: "always" do |ansible|
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbooks/mobile.yml"
  end
end
