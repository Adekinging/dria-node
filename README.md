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
1. Then you’ll see in the terminal that it is asking you to provide your ETH wallet private key, provide (Your metamask Private Key without 0x) 

2. After that you’ll see in the terminal that it is asking you to choose the model you want to serve.

- Check teams guide before picking a model

![
](<img/model type 1.png>)

![alt text](<img/model type 2.png>)


_Just copy the model id you want to serve from the given list, then past it into the terminal, and run the command._


- You can either set an open-source model via Ollama or connect your node to an OpenAI model by defining your OpenAI API Key. To decide which one to use:

_**Ollama:**_ Free to run an AI model but requires memory on your device to be able to download and run the model itself.

_**OpenAI:**_ It has a tiny cost to run the model and therefore complete the tasks given by the DKN but the only requirement is to define an API Key.

But if you choose to serve an open model via Ollama, you’ll see something similar to this screenshot.
![alt text](<img/ollama pick.webp>)

Then the terminal will ask for API keys for Jina and Serper tools. You can simply press enter to skip these questions or type your API keys if you want to connect these tools to your node as well.

Now your node should be up and running, so you should see something like this.
![alt text](<img/node running.webp>)

Once you’re done setting up a node, you can fill out this [**form**](https://dria.ai/keeper) to get the **Node Keeper** role in our [**Discord**](https://discord.gg/dria).
