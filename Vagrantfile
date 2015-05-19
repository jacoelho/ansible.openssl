# -*- mode: ruby -*-
# vi: set ft=ruby :

RAM = 389

Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/ubuntu1404"

  config.vm.provider :virtualbox do |v|
    v.check_guest_additions = false
    v.customize ["modifyvm", :id, "--cpus", "1", "--memory", RAM]
  end

  config.vm.hostname = "openssl"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "tests/playbook.yml"
    ansible.verbose = "vvvv"
    ansible.sudo = true
  end
end
