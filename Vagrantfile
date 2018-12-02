# -*- mode: ruby -*-
# vi: set ft=ruby :

# Configurações genericas
VAGRANT_VM_PROVIDER = "virtualbox"

# Configuração ELK
MEMORIA = 6144
VERSAO_VM = "ubuntu/xenial64"


Vagrant.configure("2") do |config|

    config.vm.box = VERSAO_VM
    config.vm.hostname = "elk"
    config.ssh.insert_key = false
    config.vm.network "private_network", ip: "10.0.30.5"
    #config.vm.network "forwarded_port", guest: 80, host: 8080

    # Forward para Elasticseach
    config.vm.network "forwarded_port", guest: 9200, host: 9200
    config.vm.network "forwarded_port", guest: 9300, host: 9300

    # Forward para Kibana
    config.vm.network "forwarded_port", guest: 5601, host: 5601

    # Forward para Logstash
    #config.vm.network "forwarded_port", guest: 5044, host: 5044
    #config.vm.network "forwarded_port", guest: 9600, host: 9600

    config.vm.provider VAGRANT_VM_PROVIDER do |vb|
      vb.memory = MEMORIA
    end

end
