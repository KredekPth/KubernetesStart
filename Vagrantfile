IMAGE_NAME = "centos/7"
NODE_NUMBER = 1
API_VERSION = "2"

Vagrant.configure(API_VERSION) do |config|
    config.ssh.insert_key = false

    config.vm.provider "virtualbox" do |v|
        v.memory = 2048
        v.cpus = 2
    end
      
    config.vm.define "KUBERNETES-MASTER" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "192.168.10.10"
        master.vm.hostname = "master"
        master.vm.provision "ansible" do |ansible|
            ansible.playbook = "playbooks/master.yml"
            ansible.extra_vars = {
                node_ip: "192.168.10.10",
            }
        end
    end

    (1..NODE_NUMBER).each do |i|
        config.vm.define "KUBERENETES-NODE-#{i}" do |node|
            node.vm.box = IMAGE_NAME
            node.vm.network "private_network", ip: "192.168.10.#{i + 10}"
            node.vm.hostname = "node-#{i}"
            node.vm.provision "ansible" do |ansible|
                ansible.playbook = "playbooks/node.yml"
                ansible.extra_vars = {
                    node_ip: "192.168.10.#{i + 10}",
                }
            end
        end
    end
end