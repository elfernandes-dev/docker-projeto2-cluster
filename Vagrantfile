machines = {
  "master" => {"memory" => "512", "cpu" => "1", 'ip' => '200', "image" => "ubuntu/focal64"},
  "node01" => {"memory" => "512", "cpu" => "1", 'ip' => '201', "image" => "ubuntu/focal64"}
}

Vagrant.configure("2") do |config|

  machines.each do |name, conf|
    config.vm.define "#{name}" do |machine|
      machine.vm.box = "#{conf["image"]}"
      machine.vm.hostname = "#{name}"
      machine.vm.network "public_network", ip: "192.168.0.#{conf['ip']}"
      machine.vm.provider "virtualbox" do |vb|
        vb.name = "#{name}"
        vb.memory = conf["memory"]
        vb.cpus = conf["cpu"]
        
      end
      machine.vm.provision "shell", path: "instalar-docker.sh"  
      if "#{name}" == "master"
        machine.vm.provision "shell", path: "master.sh"
      else
        machine.vm.provision "shell", path: "nodes.sh"
      end 
    end
  end
end