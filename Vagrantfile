# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  #образ вм машины с вагранд клауд
  config.vm.box = "hashicorp/bionic64"
  #настройки вм и выбор провайдера
  config.vm.provider "virtualbox" do |vb|
  #отключаем интерфейс
  vb.gui = false
  # выделяем 2гб ОЗУ
  vb.memory = "2048"
  # выделяем одноядерный процессор
  vb.cpus = 1

  config.vm.hostname = "VagrantVM"
  

  # переброс портов
  config.vm.network "forwarded_port", guest: 3306, host: 33060
  config.vm.network "forwarded_port", guest: 80, host: 8000
  # для настройки сети
  config.vm.network "private_network", ip: "192.168.0.155"
  # команда, которая выполнится после создания машины
  config.vm.provision "shell", path: "provision.sh"
  end
end
