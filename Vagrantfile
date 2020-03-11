Vagrant.configure("2") do |config|

      config.vm.define vm_name= "yordanVM" do |node|
        node.vm.box = "yordan/box"
        node.vm.hostname = vm_name
      end
      config.vm.provider "virtualbox" do |v|
        v.name = "yordanVM"
        v.memory = 2048
        v.cpus = 2
      end
    end
      