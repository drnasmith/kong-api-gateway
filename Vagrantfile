# For shared folders use geerlingguy/centos7 instead of centos/7
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "kong" do |kong|
    # Either use private network or expose ports on localhost
    kong.vm.network "private_network", ip: "192.168.33.100"
    kong.vm.hostname="kong.example.org"

    # Comment out next two definitions if on Windows
    kong.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbooks/kong.yml"
    end
  end

end
