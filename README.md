# TensorflowLearning
This is about the installation and use of google Tensorflow

the installation of tensorflow without root permission

1. download tensorflow source 
  Clone the TensorFlow repository

   $ git clone --recurse-submodules https://github.com/tensorflow/tensorflow  (Ubuntu)
    --recurse-submodules is required to fetch the protobuf library that TensorFlow depends on.
 for CentOS 6, git clone --recursive https://github.com/tensorflow/tensorflow
 
 we can't connect github in our server, so download its zip folder in other computer, then upload to the server

2. install without root permission
$ unzip tensorflow-master.zip
#####
.....
   creating: tensorflow-master/third_party/gpus/                                                              
   creating: tensorflow-master/third_party/gpus/crosstool/
  inflating: tensorflow-master/third_party/gpus/crosstool/BUILD
  inflating: tensorflow-master/third_party/gpus/crosstool/CROSSTOOL
  inflating: tensorflow-master/third_party/gpus/crosstool/LICENSE
   creating: tensorflow-master/third_party/gpus/crosstool/clang/
.....
#####
$ cd tensorflow-master
$ ./configure --prefix=/..../tensorflow_master_installation/   specify the installation place
here the CUDA location need to be specified
####
Do you wish to build TensorFlow with GPU support? [y/n] y
GPU support will be enabled for TensorFlow

Please specify the location where CUDA 7.0 toolkit is installed. Refer to README.md for more details. [Default is /usr/local/cuda]:
####

3. install the CUDA Tookit 7.0
 In our cluster, there is CUDA Tookit 6.0. But CUDA Tookit 7.0 is needed in Tensorflow. The adiminister of cluster consider the stable, so he doesn't agree with installing CUDA Tookit 7.0 with root. My strategy is that installing it in my account.
 a) download https://developer.nvidia.com/cuda-toolkit-70,  the format *.run is chose.

4. instal CUDNN Toolkit 6.5
