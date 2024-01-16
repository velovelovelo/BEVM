# BEVM
BEVM Incentivized Node Testnet (BTC Layer2)

### System Requirements ###
- OS : Ubuntu 20.4+
- CPU : 2 Cores
- RAM : 2 GB
- SSD : 300 GB

### installation ###
There are 2 different ways to run an BEVM node:
- Using Docker
- Using Binary



### 1.Running with docker ###

### Installation

update dependencies
```
sudo apt update -y
```

Download the installation shell of docker officially
```
curl -fsSL https://get.docker.com -o get-docker.sh
```
run the shell

```
sudo sh get-docker.sh
```

### Establish a host mapping path
Find a path that is used to store data on your VPS, for example:
```
cd /var/lib
```
Make a new directory, and remember your path

```
mkdir node_bevm_test_storage
```
Fetch the docker image

```
sudo docker pull btclayer2/bevm:v0.1.1
```

### Run a docker container
if you set your own hosting map path, you will replace "/var/lib/node_bevm_test_storage" on your own and you need to replace "your_node_name" to the name you fancy.

```
sudo docker run -d -v /var/lib/node_bevm_test_storage:/root/.local/share/bevm btclayer2/bevm:v0.1.1 bevm "--chain=testnet" "--name=your_node_name" "--pruning=archive" --telemetry-url "wss://telemetry.bevm.io/submit 0"
```
If you want to get incentives from the BEVM TestNet FullNode Program, set "your_node_name" as the BEVM address.

### Check it on the telemetry 
Open https://telemetry.bevm.io/ to check your node state.




### 2.Running with Binary ###
### Install BEVM Node
Download the latest stable release of the BEVM node from the builds repo and unpack.Make sure you're running Ubuntu system.Choose the corresponding binary package according to your operating system architecture.
- X86 : https://github.com/btclayer2/BEVM/releases/download/testnet-v0.1.1/bevm-v0.1.1-ubuntu20.04
- arm 64 : https://github.com/btclayer2/BEVM/releases/download/testnet-v0.1.1/bevm-v0.1.1-ubuntu20.04.1-arm64

  Unzip the downloaded package then you can try to run the node:
  ```
  $ bevm --version
  bevm 0.1.1-ef190a5a903
  ```


### Run node ###

```
$ bevm --chain=testnet --name="Your Node Name" --pruning=archive --telemetry-url "wss://telemetry.bevm.io/submit 0"
```
*If you want to get incentives from the BEVM TestNet FullNode Program, set "your_node_name" as the BEVM address.*


### Telemetry stats ###
*If your deployment is successful, you can see the running status of your node on Telemetry stats : https://telemetry.bevm.io/*
                                

