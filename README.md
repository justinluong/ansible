# Ansible Setup
```bash
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt update -y
sudo apt install -y curl git software-properties-common ansible vim tmux
```

Run playbooks straight from git using `ansible-pull`. Otherwise clone or copy and paste the playbooks to the local machine.

# Skipping tags
Sometimes commands will fail if they've already been run. To skip tags, use the `--skip-tags` option.
```bash
ansible-pull -U https://github.com/justinluong/ansible.git debian-setup.yaml --skip-tags "pyenv"
```

# Create Debian 12 container for testing
1. Pull image
```
docker pull debian:bookworm-slim
```
2. Create container that will be removed after exit
```
docker run -it --rm debian:bookworm-slim bash -c "apt update && apt install -y sudo && bash"
```

# Debian Setup
Installs both pyenv and mamba to manage python. Mamba's path is added to the end of the PATH variable to ensure pyenv is used first.
```bash
ansible-pull -U https://github.com/justinluong/ansible.git debian-setup.yaml
```

# Git Setup(s)
```bash
ansible-pull -U https://github.com/justinluong/ansible.git git-setup-wx.yaml
```
```bash
ansible-pull -U https://github.com/justinluong/ansible.git git-setup.yaml
```
