Vagrant.configure("2") do |config|
  config.vm.box = "generic/debian10"
  config.vm.provider "virtualbox" do |v|
    # v.gui = true
    v.name = "m08uf1pr2"
    v.memory = 2048
    v.cpus = 1
    v.customize ['modifyvm', :id, '--clipboard', 'bidirectional']     
  end

  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 8888, host: 8888
  
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update -y
    sudo apt-get upgrade -y
    sudo apt-get install -y net-tools
    sudo apt-get install -y apache2 apache2-doc
    sudo apt-get install -y libapache2-mod-php
    sudo apt-get install -y php7.3 
  SHELL

end
