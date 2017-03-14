Vagrant.configure("2") do |config|
  config.vm.box = "second-box-jekyll.box"
    config.ssh.private_key_path = "~/.ssh/blindij"
  config.vm.network :forwarded_port, guest:4000, host:9191, host_ip: "127.0.0.1"
end
