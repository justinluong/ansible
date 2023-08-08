# Ansible Setup

```bash
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt update -y
sudo apt install -y curl git software-properties-common ansible
sudo ansible-pull -U https://github.com/justinluong/ansible.git
```

# Create new container for testing

```
docker run -it --rm debian:bullseye-slim /bin/bash
```

# Debian Setup
Installs both pyenv and mamba to manage python. Mamba's path is added to the end of the PATH variable to ensure pyenv is used first.