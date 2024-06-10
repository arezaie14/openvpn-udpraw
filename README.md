# OpenVpn Tunnel

This is for who needs to bypass internet limitations.

## Requirements
Docker installed

Docker compose installed
## Usage
Change .env file as your needed:
```c++
SERVER_ADDRESS= 12.34.56.78 //The server ip with global internet access
SERVER_PORT=1234            //The port that you need to expose it should below 65535
PASSWORD="pass123"          //The password for safe tunnel it can be every thing
CLIENT_ADDRESS=44.33.55.11  //The server to tunnel with inside country 
SUBNET=10.5.0.0             //internal subnet of docker.  ***optional
GATEWAY=10.5.0.1            //internal gateway of docker. ***optional 
UDP_SPEEDER_IP=10.5.0.4     //udp_speeder internal ip.    ***optional
UDP_RAW_IP=10.5.0.3         //udpraw internal ip.         ***optional
WG_IP=10.5.0.2              //OpenVpn internal ip.        ***optional
```
#### On server with global internet access:
Clone project:

```c++
git clone git@github.com:arezaie14/openvpn-udpraw.git
cd ./openvpn-udpraw
chmod +x ./server.run.sh
./server.run.sh
```
#### On server with internet limitation:
Clone project:

```c++
git clone git@github.com:arezaie14/openvpn-udpraw.git
cd ./openvpn-udpraw
chmod +x ./client.run.sh
./client.run.sh
```


## How its working

OpenVpn_client-->udpspeeder_client-->udp2raw_client---------(internet)---------->udp2raw_server-->udpspeeder_server-->OpenVpn_server

#### You can find it: [here](https://github.com/wangyu-/udp2raw/wiki/bypass-mtu-limitation)
