# Object detection to prevent finger injuries

Object detection applications to prevent finger injuries in a cutting tool holder environment

research project while in University of Stuttgart

## Tabels of Contents




## Background





## Hardware
1. Jetson Nano Developer Kit 4GB
2. Micro SD card above 32GB
3. USB Webcam
4. Breadboard, jumper wires, resistance and LED (for GPIO)

## Setup
follow the official guide to boot Jetson Nano [Getting Started with Jetson Nano Developer Kit](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit)

## Library Installation
### 1. update and upgrade
```
sudo apt-get update
sudo apt-get upgrade
```
### 2. add cuda PATH
```
cd ~
gedit .bashrc
```
Add these three lines at the end, Ctrl+S to save and close gedit

>export PATH=/usr/local/cuda/bin:$PATH
>
>export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
>
>export CUDA_ROOT=/usr/local/cuda

Activate and reboot
```
source .bashrc
reboot
```

### 3. install pytorch 1.8 and torchvision v0.9.0 via [PyTorch for Jetson - version 1.10 now available](https://forums.developer.nvidia.com/t/pytorch-for-jetson-version-1-10-now-available/72048)
```
wget https://nvidia.box.com/shared/static/p57jwntv436lfrd78inwl7iml6p13fzh.whl -O torch-1.8.0-cp36-cp36m-linux_aarch64.whl
sudo apt-get install python3-pip libopenblas-base libopenmpi-dev 
pip3 install Cython
pip3 install numpy torch-1.8.0-cp36-cp36m-linux_aarch64.whl
```
```
sudo apt-get install libjpeg-dev zlib1g-dev libpython3-dev libavcodec-dev libavformat-dev libswscale-dev
git clone --branch v0.9.0 https://github.com/pytorch/vision torchvision   
cd torchvision
export BUILD_VERSION=0.9.0 
python3 setup.py install --user
```
### 4. install yolov5
install dependency
```
sudo apt-get install liblapack-dev
sudo apt-get install libblas-dev
sudo apt-get install gfortran	
```
install scipy matplotlib pillow pyyaml tensorboard tqdm
```
pip3 install scipy matplotlib pillow pyyaml tensorboard tqdm
```
install pillow correctly
```
pip3 uninstall pillow
pip3 install pillow --no-cache-dir
```
