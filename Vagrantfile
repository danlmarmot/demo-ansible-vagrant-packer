VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "webserver" do |webserver|
    webserver.vm.box = "ubuntu/trusty64"
    webserver.vm.network :private_network, ip: "192.168.111.222"
    webserver.vm.network :forwarded_port, guest: 8080, host: 8080
    webserver.vm.provision "ansible" do |ansible|
      ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
      ansible.verbose = "v"
      ansible.playbook = "webserver.yml"
    end
  end
end