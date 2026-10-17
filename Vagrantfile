# Провайдер из переменной окружения или virtualbox по умолчанию
PROVIDER = ENV["VAGRANT_DEFAULT_PROVIDER"] || "virtualbox"

# Имя бокса можно переопределить через переменную окружения:
#   VAGRANT_BOX=almalinux9-stand vagrant up --provider=libvirt
BOX_NAME = ENV['VAGRANT_BOX'] || 'generic/ubuntu2204'

MACHINES = {
  :"pam" => {
    :box_name => BOX_NAME,
    :cpus     => 2,
    :memory   => 1024,
    :ip       => "192.168.57.10",
  }
}

Vagrant.configure("2") do |config|
  # Глобальные настройки (если нужны)
  config.vm.synced_folder ".", "/vagrant", disabled: true

  MACHINES.each do |name, boxconfig|
    config.vm.define name.to_s do |box|
      box.vm.box = boxconfig[:box_name]
      box.vm.box_version = boxconfig[:box_version] if boxconfig[:box_version]
      box.vm.hostname = name.to_s

      # --- Сеть (только для этой машины) ---
      box.vm.network "private_network", ip: boxconfig[:ip]

      # --- Провайдер VirtualBox ---
      box.vm.provider :virtualbox do |vb|
        vb.memory = boxconfig[:memory]
        vb.cpus = boxconfig[:cpus]
      end

      # --- Провайдер libvirt ---
      box.vm.provider :libvirt do |lv|
        lv.memory = boxconfig[:memory]
        lv.cpus = boxconfig[:cpus]
        # libvirt по умолчанию создаёт сеть, можно дополнительно задать network_name при необходимости
      end

      # --- Провижининг: включить PasswordAuthentication ---
      box.vm.provision "shell", inline: <<-SHELL
        if [ -f /etc/ssh/sshd_config ]; then
          sed -i 's/^#*PasswordAuthentication.*/PasswordAuthentication yes/' /etc/ssh/sshd_config
          if command -v systemctl >/dev/null 2>&1; then
            systemctl restart sshd
          elif command -v service >/dev/null 2>&1; then
            service sshd restart
          fi
        fi
      SHELL
    end
  end
end
