cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
set(CMAKE_CUDA_COMPILER "C:/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v11.6/bin/nvcc.exe")
project(cudaVStemplate LANGUAGES CXX CUDA)
set(CMAKE_CUDA_FLAGS ${CMAKE_CUDA_FLAGS} "-g -G")  # enable cuda-gdb
set(CMAKE_CUDA_STANDARD 11)


include_directories(${PROJECT_SOURCE_DIR}/include)
link_directories(${PROJECT_SOURCE_DIR}/lib)

#thrust, cub  
include_directories(C:/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v11.6/include/)
include_directories(${PROJECT_SOURCE_DIR}/include/cuda-11.6-header/)

#CUDA
link_directories(C:/Program Files/NVIDIA GPU Computing Toolkit/CUDA/v11.6/lib/x64)
link_directories(${PROJECT_SOURCE_DIR}/lib/cuda-11.6-lib/x64/)


set(BUILD_TEST "ON")
set(CUDA_TEST "ON")

if(BUILD_TEST)
  message("BUILD_TEST")



else()
  message("Welcome !!!")
endif()


if(CUDA_TEST)
add_executable(basic_vector "cuda-example/basic_vector.cu")
target_compile_features(basic_vector PUBLIC cxx_std_11)

# Required for CUDA builds
set_target_properties(basic_vector PROPERTIES CUDA_SEPARABLE_COMPILATION  ON)
else()
  message("CUDA!!!")
endif()

add_executable (main "main.cpp" )
target_link_libraries( main  )

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET main PROPERTY CXX_STANDARD 20)
endif()

