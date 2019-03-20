# [DroNet: Efficient Convolutional Neural Network Detector for Real-Time UAV Applications](Paper/DroNet.pdf)
Implementation of the CNN Car Detector proposed on DroNet paper using [Darknet](https://github.com/pjreddie/darknet) Framework.

![DroNetV3 - Crossroad](Paper/DroNet.gif)


## Dependencies
> [OpenCV](https://opencv.org/)


> [CUDA(Optional)](https://developer.nvidia.com/cuda-downloads)

## Build

> In order to build DarkNet library and use our DroNet CNN you need to build OpenCV using [these](https://docs.opencv.org/2.4/doc/tutorials/introduction/linux_install/linux_install.html) Steps.
```bash
nano Makefile # run this with sudo if you have permission error
```
> To build DroNet on Mac OS please comment out line 22 and uncomment line 23 and update the path of GCC
- GPU=0 - enable/disable GPU (To use GPU modify line 50 and 52 with include and lib64 CUDA path)
- CUDNN=0 - enable/disable CUDNN
- OPENCV=1 - enable/disable OpenCV
- OPENMP=1 - enable/disable Multi-Processing on CPU
- DEBUG=0 - enable/disable Debug mode (Never used)
```bash
make -j
```
### DroNetV1 - Works better with low altitudes
```bash
./darknet detector demo car.data cfg/DroNet_car.cfg results/DroNet_car.weights Car_Parking.mov -thresh 0.4
./darknet detector demo car.data cfg/DroNet_car.cfg results/DroNet_car.weights Car_Road.MOV -thresh 0.4
```

### DroNetV3 - Works better with higher altitudes (Recommended .cfg input 1024 x 1024)
```bash
./darknet detector demo car_ped.data cfg/DroNetV3_car.cfg results/DroNetV3_car.weights Car_Crossroad.mp4
```
