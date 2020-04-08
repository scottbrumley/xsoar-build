# Build Demisto Attack box for running scripted attacks against Cortex XDR hosts


Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.hostname = "demisto"
  config.vm.provider :virtualbox do |v|
     v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
     v.customize ["modifyvm", :id, "--memory", 4096]
     v.customize ["modifyvm", :id, "--name", "demisto"]

  end
  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.provision "shell", path: "scripts/bootstrap.sh", privileged: true
end