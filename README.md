

## Installation

### Kali Linux / Ubuntu / Parrot OS

```bash
git clone https://github.com/yogeshpcte/yogesh.git
cd seeker/
apt update
apt install python3 python3-pip php
pip3 install requests
```

### BlackArch Linux

```bash
pacman -S seeker
```

### Termux

```bash
git clone https://github.com/yogeshpcte/yogesh.git
cd seeker/
pkg update
pkg install python php
pip3 install requests
```
### Docker

```bash
docker pull  yogeshpcte/yogesh.git
```

### OSX
```bash
git clone https://github.com/yogeshpcte/yogesh.git
cd seeker/
python3 seeker.py
````

In order to run in tunnel mode, install ngrok by running this command in the terminal:
```bash
brew install ngrok/ngrok/ngrok

ngrok http 8080
````

## Usage

```bash
python3 yogesh.py -h

usage: yogesh.py [-h] [-s SUBDOMAIN]

optional arguments:
  -h, --help            show this help message and exit
  -k KML, --kml         Provide KML Filename ( Optional )
  -p PORT, --port       Port for Web Server [ Default : 8080 ]
  -t TUNNEL, --tunnel   Specify Tunnel Mode [ Available : manual ]

##################
# Usage Examples #
##################

# Step 1 : In first terminal
$ python3 yogesh.py -t manual

# Step 2 : In second terminal start a tunnel service such as ngrok
$ ./ngrok http 8080

###########
# Options #
###########

# Ouput KML File for Google Earth
$ python3 yogesh.py -t manual -k <filename>

# Use Custom Port
$ python3 yogesh.py -t manual -p 1337
$ ./ngrok http 1337

################
# Docker Usage #
################

# Step 1
$ docker network create ngroknet

# Step 2
$ docker run --rm -it --net ngroknet --name seeker yogeshpcte/yogesh.git

# Step 3
$ docker run --rm -it --net ngroknet --name ngrok wernight/ngrok ngrok http seeker:8080
```
