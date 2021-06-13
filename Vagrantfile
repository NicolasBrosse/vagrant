# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/groovy64"
  config.vm.hostname = "machine1"
  config.vm.network "private_network", ip: "192.168.0.66"
  
  # Configuration de Virtualbox. Voir https://www.vagrantup.com/docs/providers/virtualbox/configuration
  config.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu-groovy"
    vb.memory = "1024"
    vb.cpus = "1"
  end

  # Pour faire en sorte de pouvoir se connecter en ssh avec vagrant@ directement et non via la commande vagrant ssh
  config.vm.provision "shell", inline: <<-SHELL
    sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config    
    service ssh restart
  SHELL

end