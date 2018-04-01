Vagrant.configure(2) do |config|
  config.vm.box = "debian/jessie64"
  
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.groups = {
      "web" => ["master"],
      "agent" => ["agent1", "agent2"],
      "agent:vars" => {
        "psdash_mode" => "agent",
        "psdash_master" => "http://192.168.50.30:5000"
      }
    }
  end

  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network "private_network", ip: "192.168.50.30"
  end

  config.vm.define "agent1" do |agent|
    agent.vm.hostname = "agent1"
    agent.vm.network "private_network", ip: "192.168.50.31"
  end

  config.vm.define "agent2" do |agent|
    agent.vm.hostname = "agent2"
    agent.vm.network "private_network", ip: "192.168.50.32"
  end

end
