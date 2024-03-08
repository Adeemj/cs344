# Work on Problem Set 1 on Google Colab GPU

This repository contains the necessary modifications to make the Problem Set compatible with Google Colab. 

## Opencv Installation on Google Colab

Install OpenCV from source. Here's how you can set up OpenCV:

### Step 1: Installing required packages and tools

```bash
sudo apt update && sudo apt install -y g++ cmake make git libgtk2.0-dev pkg-config
```
### Step 2: Download the source
```bash
git clone https://github.com/opencv/opencv.git
```
### Step 3: Build and Install
```bash
mkdir -p build && cd build
cmake ../opencv -DBUILD_LIST=core,imgproc,imgcodecs 
make -j$(nproc) 
sudo make install
```

### Step 4: Set Library Paths
```bash
export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
```

## Run Problem Set 1

### Code Completion
Prior to building the application, ensure that you have implemented all necessary functionality within student_func.cu.

### Compile the Codebase
Use the provided Makefile to compile the problem set:
```bash
make
```
### Run the executable with the required arguments:
```bash
./HW1 {input image path}
```
Example: 
```bash
./HW1 cinque_terre_small.jpg
```

## Summary of Code Changes
1. The Makefile has been updated to use correct paths and libraires. 
2. Removed dependencies on OpenCV's GUI modules since Google Colab runs on a headless server.
3. OpenCV syntax in the codebase has been updated to comply with the latest API standards in OpenCV 4.x.