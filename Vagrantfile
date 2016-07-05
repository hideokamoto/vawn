VAGRANTFILE_API_VERSION = "2"

Vagrant.configure( VAGRANTFILE_API_VERSION ) do | config |
	config.vm.define "vagrant" do |vagrant|
		vagrant.vm.box = "ubuntu/trusty64"
		vagrant.vm.network "private_network", ip: "192.168.33.90"
		vagrant.vm.network "forwarded_port", guest: 80, host: 8080
		vagrant.vm.network "forwarded_port", guest: 443, host:8443
		vagrant.vm.provision "ansible" do |ansible|
			ansible.playbook = "ansible.yml"
			ansible.inventory_path = "hosts"
			ansible.limit = 'all'
		end
	end
end
