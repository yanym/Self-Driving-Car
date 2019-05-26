# Self-Driving-Car

# Extract the images from rosbag(Note: Images are saved as compressed format)
1. In a terminal, run```roslaunch export.launch```
2. Open another one and run ```python extract_iamge.py```


# Some shit about Ubuntu 18.04 w/ VMWare Fusion 11

## Change Network mode to VM own network. DO NOT SHARE w/ Parent. Fucking slow.
## Install ss-qt5:
In 1804, you encounter a problem: ppa:hzwhuang/ss-qt5 : No source 

Solving steps:
cd /etc/apt/sources.list.d
(hzwhuang-ubuntu-ss-qt5-bionic.list ) change “bionic“ to “xenial” 
sudo apt-get update 
sudo apt-get install shadowsocks-qt5 


## Install polipo
sudo apt-get install polipo

sudo vim /etc/polipo/config

proxyAddress = "0.0.0.0"
socksParentProxy = “127.0.0.1:1080"
socksProxyType = socks5

export http_proxy="http://127.0.0.1:8123"
export https_proxy="http://127.0.0.1:8123"
export ftp_proxy="http://127.0.0.1:8123"

sudo service polipo start
sudo service polipo stop


## Use pip w/ proxy
pip3 --proxy 127.0.0.1:8123 install tensorflow

## Extract csv
``` rostopic echo -b <BAGFILE> -p <TOPIC> > <output>.csv # <BAGFILE> is bag file，<TOPIC> is topic ```