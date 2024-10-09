# Guide on how to run Dria node

This guide is specifically for Linux AMD 

## Install Dependecies
Install docker
```bash
sudo apt update && sudo apt upgrade -y

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo chmod +x /usr/local/bin/docker-compose
```

check docker version 
```bash
docker --version
```

Ollama
```bash
curl -fsSL https://ollama.com/install.sh | sh
```
## Install Dria
```bash
cd $HOME
curl -L -o dkn-compute-node.zip https://github.com/firstbatchxyz/dkn-compute-launcher/releases/latest/download/dkn-compute-launcher-linux-amd64.zip
```
```bash
unzip dkn-compute-node.zip
```
```bash
cd dkn-compute-node
```

## Kickstart your Dria Node
```bash
./dkn-compute-launcher
```
Then you’ll see in the terminal that it is asking you to provide your ETH wallet private key. 

After that you’ll see in the terminal that it is asking you to choose the model you want to serve.

Just copy the model id you want to serve from the given list, then past it into the terminal, and run the command. 

