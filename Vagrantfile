Vagrant.configure("2") do |config|

    config.vm.define "db" do |db|
        db.vm.box = "ubuntu/xenial64"
        db.vm.network "private_network", ip: "192.168.10.150"
        db.vm.synced_folder "config_files", "/home/vagrant/config_files"
        db.vm.provision "shell", path: "db/provision_DB.sh"
    end
    config.vm.define "app" do |app|
        app.vm.box = "ubuntu/xenial64"
        app.vm.network "private_network", ip: "192.168.10.100"
        app.vm.synced_folder "app", "/home/ubuntu/app"
        app.vm.provision "shell", path: "provision.sh"
        app.vm.synced_folder "config_files", "/home/vagrant/config_files"

    end
    
end
