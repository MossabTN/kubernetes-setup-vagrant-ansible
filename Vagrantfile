IMAGE_NAME = "bento/ubuntu-16.04"
N = 3

Vagrant.configure("2") do |config|
    config.ssh.insert_key = false

    #config.vm.define "loadbalancer" do |loadbalancer|
    #    loadbalancer.vm.box = "ubuntu/trusty64"
    #    loadbalancer.vm.network "private_network", ip: "192.168.50.5"
    #    loadbalancer.vm.provider "virtualbox" do |v|
    #    	v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    #    	v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
    #    end
    #    loadbalancer.vm.provision "ansible" do |ansible|
    #        ansible.playbook = "haproxy.yml"
    #    end
    #end

    config.vm.define "nfs-server" do |node|
        node.vm.provider "virtualbox" do |v|
            v.memory = 2048
            v.cpus = 2
        end
        node.vm.box = IMAGE_NAME
        node.vm.network "private_network", ip: "192.168.50.8"
        node.vm.hostname = "nfs-server"
        node.vm.provision "ansible" do |ansible|
            ansible.playbook = "kubernetes-setup/nfs-playbook.yml"
            ansible.extra_vars = {
                node_ip: "192.168.50.8",
            }
        end
    end
      
    config.vm.define "k8s-master" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: "192.168.50.10"
        #master.vm.network "forwarded_port", guest: 6443, host: 6443
        master.vm.hostname = "k8s-master"
        master.vm.provider "virtualbox" do |v|
        	v.memory = 3072
        	v.cpus = 2
        	v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        	v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
        end
        master.vm.provision "ansible" do |ansible|
            ansible.playbook = "kubernetes-setup/master-playbook.yml"
            ansible.extra_vars = {
                node_ip: "192.168.50.10",
            }
        end
    end

    (1..N).each do |i|
        config.vm.define "node-#{i}" do |node|
            node.vm.box = IMAGE_NAME
            node.vm.network "private_network", ip: "192.168.50.#{i + 10}"
            node.vm.hostname = "node-#{i}"
            node.vm.provider "virtualbox" do |v|
                v.linked_clone = true
                v.memory = 6144
                v.cpus = 2
            end
            node.vm.provision "ansible" do |ansible|
                ansible.playbook = "kubernetes-setup/node-playbook.yml"
                ansible.extra_vars = {
                    node_ip: "192.168.50.#{i + 10}",
                }
            end
        end
    end

end