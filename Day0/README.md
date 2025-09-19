# Week0:Tool Installation(Yosys, Iverilog , Gtkwave)

## 1.Oracle Virtual Box installed
  (https://www.virtualbox.org/wiki/Downloads )

## 2.System Installation
  6GB RAM, 50 GB HDD 
  ,Ubuntu 20.04+ 
  ,4vCPU

## 3.Tools installation 

### Yosys
```bash
$ sudo apt-get update 
$ git clone https://github.com/YosysHQ/yosys.git 
$ cd yosys 
$ sudo apt install make (If make is not installed please install it)  
$ sudo apt-get install build-essential clang bison flex \ 
libreadline-dev gawk tcl-dev libffi-dev git \ 
graphviz xdot pkg-config python3 libboost-system-dev \ 
libboost-python-dev libboost-filesystem-dev zlib1g-dev 
$ make config-gcc 
$ make  
$ sudo make install
```

![Alt text](IMAGES/Screenshot%from%2025-09-19%14-58-59.png)



