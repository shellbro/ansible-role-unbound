Vagrant.configure("2") do |config|
  config.vbguest.auto_update = false
  
  config.vm.define "centos" do |centos|
    centos.vm.box = "centos/7"
    centos.vm.network "forwarded_port", guest: 53, host: 12353, host_ip: "127.0.0.1", protocol: "tcp"
    centos.vm.network "forwarded_port", guest: 53, host: 12353, host_ip: "127.0.0.1", protocol: "udp"
    centos.vm.provision "ansible" do |a|
      a.limit = "all"
      a.playbook = "tests/test.yml"
    end
    centos.vm.synced_folder ".", "/vagrant", disabled: true
  end
end
