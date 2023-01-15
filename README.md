# Updating/Installing Go in WSL

## Remove

Removes older versions if they are present

```commandline
sudo rm -rf /usr/local/go\* && sudo rm -rf /usr/local/go
```

## Install

Change version as applicable

```commandline
VERSION=1.19
OS=linux
ARCH=amd64

cd $HOME
wget https://storage.googleapis.com/golang/go$VERSION.$OS-$ARCH.tar.gz
tar -xvf go$VERSION.$OS-$ARCH.tar.gz
mv go go-$VERSION
sudo mv go-$VERSION /usr/local
```

## Add Go Environment

Open up `~/.bashrc` and update/add the following near the bottom (replace with correct go version)

```commandline
# configure go-1.19

export GOROOT=/usr/local/go-1.19
export GOPATH=$HOME/projects/go
export GOBIN=$GOPATH/bin
export PATH=$PATH:$GOROOT/bin
export PATH=$PATH:$HOME/projects/go/bin
```
