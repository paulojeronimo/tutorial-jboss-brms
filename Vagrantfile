# -*- mode: ruby -*-
# vi: set ft=ruby ts=2 sw=2 expandtab:

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "boxcutter/fedora21"

  # Desabilita a atualização automática do VirtualBox Guest Additions
  # feita pelo plugin vbguest - https://github.com/dotless-de/vagrant-vbguest
  #config.vbguest.auto_update = false

  # Exporta portas utilizadas pelo WildFly
  config.vm.network :forwarded_port, guest: 8080, host: 8080
  config.vm.network :forwarded_port, guest: 9990, host: 9990

  config.vm.provider "virtualbox" do |v|
    #v.gui = true
    v.memory = 4096 
  end

  # Local comum para os diretórios compartilhados entre os ambientes
  config.vm.synced_folder "../tutorial-jboss-brms.backup", "/backup", create: true

  #config.vm.provision "shell" do |s|
  #  s.path = "instalar"
  #  s.privileged = false
  #end
end
