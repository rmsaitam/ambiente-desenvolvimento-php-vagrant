
Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu-server-17.04"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-i386-vagrant-disk1.box"
    config.vm.network :forwarded_port, guest: 80, host: 8080
     config.vm.network :forwarded_port, guest: 22, host: 2222, id: "ssh", disabled: true
     config.vm.network :forwarded_port, guest: 22, host: 2222, auto_correct: true
    config.vm.network :private_network, ip: "192.168.3.10"
    config.vm.synced_folder "www/", "/var/www/html", owner: "www-data", group: "www-data", mount_options: ['dmode=777','fmode=666']
    config.vm.synced_folder "~", "/vagrant", owner: "vagrant", group: "vagrant"
    config.vm.provider "virtualbox" do |machine|
    	machine.memory = 1024
    	machine.name = "ubuntu-server-php"
    end
    config.vm.provision :shell, path: "setup.sh"
end
