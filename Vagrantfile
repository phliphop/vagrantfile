# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # MASTER
  config.vm.define "master" do |master|
    master.vm.box = "xenial_official"
    master.vm.network :private_network, ip: "192.168.0.42"
    # config.vm.network "forwarded_port", guest: 80, host: 8080
    master.vm.define "master"

    master.vm.provider :virtualbox do |vb|
      vb.customize [
        "modifyvm", :id,
        "--cpuexecutioncap", "50",
        "--memory", "1024",
      ]   
    end 
  end 
  # SLAVE 
  config.vm.define "slave" do |slave|
    slave.vm.box = "xenial_official"
    slave.vm.network :private_network, ip: "192.168.0.43"
    slave.vm.network "forwarded_port", guest: 80, host: 8080
    slave.vm.define "slave"

    slave.vm.provider :virtualbox do |vb|
      vb.customize [
        "modifyvm", :id,
        "--cpuexecutioncap", "50",
        "--memory", "1024",
      ]   
    end 
  end 

end
