# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2204"
  
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 2

    # Додавання 4 додаткових дисків по 400MB
    (1..4).each do |i|
      vb.customize ['createhd', '--filename', "./disk#{i}.vdi", '--size', 400] # 400MB
      vb.customize ['storageattach', :id, '--storagectl', 'SATA Controller', '--port', i,
                    '--device', 0, '--type', 'hdd', '--medium', "./disk#{i}.vdi"]
    end
  end
end

