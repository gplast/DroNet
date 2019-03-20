# [DroNet: Efficient Convolutional Neural Network Detector for Real-Time UAV Applications](Paper/DroNet.pdf)
Implementation of the CNN Car Detector proposed on DroNet paper using [DarkNet](https://github.com/pjreddie/darknet) Framework.

[DroNet Performance CPU](Paper/DroNet.mp4)


## Dependencies
> [OpenCV](https://opencv.org/)


> [CUDA(Optional)](https://developer.nvidia.com/cuda-downloads)

## Build

> In order to build DarkNet library and use our DroNet CNN you need to build OpenCV using [these](https://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html) Steps.
1. sudo nano Makefile
> To build DroNet on Mac OS please comment out line 22 and uncomment line 23 and update the path of GCC
- GPU=0 - enable/disable GPU (To use GPU modify line 50 and 52 with include and lib64 CUDA path)
- CUDNN=0 - enable/disable CUDNN
- OPENCV=1 - enable/disable OpenCV
- OPENMP=1 - enable/disable Multi-Processing on CPU
- DEBUG=0 - enable/disable Debug mode (Never used)
2. sudo make -j
3. sudo ./darknet detector demo obj.data cfg/drone_net_last.cfg results/drone_net_last.weights Car_Parking.mov
4. sudo ./darknet detector demo obj.data cfg/drone_net_last.cfg results/drone_net_last.weights Car_Road.MOV
