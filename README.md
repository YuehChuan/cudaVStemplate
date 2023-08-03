# cudaVStemplate
Visual Studio2022  cuda11.6  win10

### "CUDA compiler identification source file "CMakeCUDACompilerId.cu" missing"
CMake project under Visual Studio 2022 windows10 hits this.

### The main issue is IDE.
Visual Studio 2022 support CUDA 11.6 above.

Check here

https://forums.developer.nvidia.com/t/visual-studio-2022-cuda-toolkit-support/197578
https://forums.developer.nvidia.com/t/visual-studio-2022-cuda-toolkit-support/197578
https://docs.nvidia.com/cuda/archive/11.5.2/cuda-installation-guide-microsoft-windows/index.html
https://developer.nvidia.com/cuda-toolkit-archive


#### None of these are solutions, so I post this.

https://github.com/NVlabs/instant-ngp/issues/126

https://github.com/NVlabs/instant-ngp/issues/923

https://blog.csdn.net/qq_26157437/article/details/129834852

![cuda](https://github.com/YuehChuan/cudaVStemplate/assets/7314531/f34ab26c-7415-4f52-afdc-0ef3a89c7c65)

## How to fly 

Simpily open the cudaVStemplate folder with Visual Studio, 
this project use CMake not .sln. 

Make sure the correspondent Cuda version in the CMakeLists.txt. (>=11.6)

Hit compile the solution button.

basic_vector.cu uses header only Cuda library thrust to make sure the environment works.

![step](https://github.com/YuehChuan/cudaVStemplate/assets/7314531/955c20fa-e5a3-4872-a19d-f5e2536de55b)

![step2](https://github.com/YuehChuan/cudaVStemplate/assets/7314531/a0c28995-ac9e-47ec-95eb-3b434e13fda8)
