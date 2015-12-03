# TensorflowLearning
This is about the installation and use of google Tensorflow

the installation of tensorflow without root permission

1. download tensorflow source 
   Clone the TensorFlow repository

    $ git clone --recurse-submodules https://github.com/tensorflow/tensorflow  (Ubuntu)
      --recurse-submodules is required to fetch the protobuf library that TensorFlow depends on.
     for CentOS 6, git clone --recursive https://github.com/tensorflow/tensorflow
 
     we can't connect github in our server, so download its zip folder in other computer, then upload to the server

2. install the CUDA Tookit 7.0
    In our cluster, there is CUDA Tookit 6.0. But CUDA Tookit 7.0 is needed in Tensorflow. The adiminister of cluster consider the       stable, so he doesn't agree with installing CUDA Tookit 7.0 with root. My strategy is that only install tookit and sdk in my     account, not drive -- several CUDA version is installed in one system, please refer to more information from  http://www.linuxdiyf.com/linux/15947.html
    a) download https://developer.nvidia.com/cuda-toolkit-70,  the format *.run is chose.
        cuda_7.0.28_linux.run    -- *.run is a script, so install by ./*.run or sh *.run
    b) $ ./cuda_7.0.28_linux.run
       Do you accept the previously read EULA? (accept/decline/quit): accept
       Install NVIDIA Accelerated Graphics Driver for Linux-x86_64 346.46? ((y)es/(n)o/(q)uit): n   -- DON'T install Driver
       Do you want to install the OpenGL libraries? ((y)es/(n)o/(q)uit) [ default is yes ]: n
       Install the CUDA 7.0 Toolkit? ((y)es/(n)o/(q)uit): y
       Enter Toolkit Location [ default is /usr/local/cuda-7.0 ]: /home/zhangli/deeplearning_home/cuda-7.0
       Do you want to install a symbolic link at /usr/local/cuda? ((y)es/(n)o/(q)uit): n
       Install the CUDA 7.0 Samples? ((y)es/(n)o/(q)uit): y
       Enter CUDA Samples Location [ default is /home/zhangli ]: /home/zhangli/deeplearning_home/
       Installing the CUDA Toolkit in /home/zhangli/deeplearnihome/cuda-7.0 ...


3. instal CUDNN Toolkit 6.5
    Download and install CUDNN Toolkit 6.5
       https://developer.nvidia.com/rdp/cudnn-archive

    Uncompress and copy the cudnn files into the toolkit directory. Assuming the toolkit is installed in /usr/local/cuda:

       tar xvzf cudnn-6.5-linux-x64-v2.tgz
       sudo cp cudnn-6.5-linux-x64-v2/cudnn.h /usr/local/cuda/include
       sudo cp cudnn-6.5-linux-x64-v2/libcudnn* /usr/local/cuda/lib64

4. install without root permission
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

     Please specify the location where CUDA 7.0 toolkit is installed. Refer to README.md for more details. [Default is /usr/local/cuda]: /home/zhangli/deeplearning_home/cuda-7.0
     Please specify the location where CUDNN 6.5 V2 library is installed. Refer to README.md for more details. [Default is   /home/zhangli/deeplearning_home/cuda-7.0]: /home/zhangli/deeplearning_home/cuda-7.0
    Setting up Cuda include
    Setting up Cuda lib64
    Setting up Cuda bin
    Setting up Cuda nvvm
     Configuration finished

     ####

5. a
