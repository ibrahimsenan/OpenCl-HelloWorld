# OpenCl-HelloWorld
Starting OpenCL on Visual Studio and It's Configuration 

 OpenCL comes as a runtime environment and has to be installed on your target machine, no matter if you are using Windows or Linux. For Mac OS X, OpenCL is already part of the system, so there is nothing to install there. The runtime installs two things: First, a dispatch library and then the actual runtime containing the implementation. The dispatch library is necessary as there is typically more than one runtime present on a machine. For instance, there might be the AMD CPU runtime and an NVIDIA GPU runtime installed at the same time. 
 The dispatcher makes sure that they don't overwrite each other.
 
 1. Getting required drives and SDK
 To get started, you need to be able to link against this dispatch library, called OpenCL.dlld on Windows. Every OpenCL SDK comes with an OpenCL.libd which allows exactly for that. The most important OpenCL SDKs right now are:
1-The Intel SDK using this link (http://software.intel.com/en-us/vcsource/tools/opencl-sdk), which works on newer Intel CPUs and integrated graphics units from Intel. It comes with OpenCL 1.2 support.
2-The AMD APP SDK using this link (http://developer.amd.com/tools/hc/AMDAPPSDK/downloads/Pages/default.aspx), which works on any CPU (both AMD and Intel) and on AMD GPUs. It supports OpenCL 1.2 as well.
3-The NVIDIA GPU SDK check (https://developer.nvidia.com/gpu-computing-sdk), which works on NVIDIA GPUs only and supports only OpenCL 1.1.
4- The OpenCL Studio (http://www.opencldev.com/), which is work on the latest NVIDIA drivers (285.62) and it's not function properly with the latest AMD Catalyst drivers (12.+). The most recent compatible driver is 11.9.

"No matter which one you choose, you have to make sure that the OpenCL.lib is found by your linker and that the headers are in your include path"

2. Linking OpenCl libs with Visual Studio
On any Visual Studio, the configurations are based on the linking with libs. Create a new Visual Studio C++ application (any template). Under src, create a new C file or Cpp it support both C/C++ . Similarly, create a kernel file by the name of kernel.cl. our main code will contain the host code. kernel.cl will contain the kernel to be executed.

- OpenCL is suggested to run on 64-bit configurations.In the Configuration Manager window you need to change from 32bit to 64bit, this to make sure that everything will work perfect.


