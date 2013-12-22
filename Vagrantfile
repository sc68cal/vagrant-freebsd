# -*- mode: ruby; -*-
Vagrant.configure("2") do |config|
  config.vm.guest = :freebsd
  config.vm.box_url = "https://masakari.coreitpro.com/files/freebsd-9.2-amd64-coreitpro.box"
  config.vm.box = "freebsd-9.2.amd64-coreitpro"
  config.vm.network "private_network", ip: "10.0.1.10"

  # Use NFS as a shared folder
  config.vm.synced_folder ".", "/vagrant", :nfs => true, id: "vagrant-root"

  config.vm.provider :virtualbox do |vb|
    # vb.customize ["startvm", :id, "--type", "gui"]
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
    vb.customize ["modifyvm", :id, "--hwvirtex", "on"]
    vb.customize ["modifyvm", :id, "--audio", "none"]
    vb.customize ["modifyvm", :id, "--nictype1", "virtio"]
    vb.customize ["modifyvm", :id, "--nictype2", "virtio"]
  end
end
