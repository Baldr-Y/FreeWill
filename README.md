# FreeWill

![futurama freewill unit](splash.jpg)

![doc build badge](https://readthedocs.org/projects/freewill/badge/?version=latest)

FreeWill is a deeplearning library implemented in C++. The purpose of writing FreeWill is for me to understand deeplearning in detail. In addition to the library itself, I will try to write detailed document and examples.

The first goal of this project is matching https://github.com/karpathy/convnetjs feature wise.

## How to build
So far, I have only tested on Ubuntu 17.10

I have been avoiding introducing dependencies to this project, but you need to have Qt5 to use it.

Make sure you have also installed Qt5

To build:

    mkdir build
    cd build
    cmake .. -DCUDA_TOOLKIT_ROOT_DIR=/usr/local/cuda-9.2 -DCMAKE_PREFIX_PATH=/home/shiy/Qt/5.11.1/gcc_64 -DCMAKE_BUILD_TYPE=debug

An example of building FreeWill on Mac OS with complex compiler setup:

    cmake .. -DCMAKE_BUILD_TYPE=debug -DCMAKE_PREFIX_PATH=/Users/shiyan/Qt/5.7/clang_64 -DCMAKE_CXX_COMPILER=/Users/shiyan/gcc7/bin/g++ -DCMAKE_C_COMPILER=/Users/shiyan/gcc7/bin/gcc -DCUDA_HOST_COMPILER=/Library/Developer/CommandLineTools/usr/bin/clang

In this case, Qt 5.7 installed with Qt installer is used. A Self-built gcc7 is used to compile c++. [A down-graded clang 3.7 is used for cuda compiling, as the newer clang isn't supported by nvcc](https://github.com/arrayfire/arrayfire/issues/1384).