---
layout: post
title: C++ Development Environment Setup for Vision, Image Processing, Graphics & Parallel Programming
tags:
  - prog
  - tut
---

C++ is an amazing programming language and the recent updates in STL with C++11
& C++14 make it even more handy. However, there are a lot of programmers
interested in using C++ that end up losing interest due to lack of a decent setup
for small programs. In this post, I am going to provide a very simple yet stable
development process that provides a way to create portable applications easily. 

> We will be using a combination of cmake, gcc, a bunch of common libraries, CUDA & git.

All these are quite used and there are very many tutorials about setting the
environments in different operating systems. We will look at each of the steps
of the dev process individually. 

C++ and libraries
------------------

If you take an
[example](http://docs.opencv.org/2.4/doc/tutorials/introduction/load_save_image/load_save_image.html) as following :

```cpp
#include <cv.h>
#include <highgui.h>

using namespace cv;

int main( int argc, char** argv )
{
 char* imageName = argv[1];
 Mat image;
 image = imread( imageName, 1 );
 if( argc != 2 || !image.data )
 {
   printf( " No image data \n " );
   return -1;
 }

 Mat gray_image;
 cvtColor( image, gray_image, CV_BGR2GRAY );
 imwrite( "Gray_Image.jpg", gray_image );
 namedWindow( imageName, CV_WINDOW_AUTOSIZE );
 namedWindow( "Gray image", CV_WINDOW_AUTOSIZE );
 imshow( imageName, image );
 imshow( "Gray image", gray_image );
 waitKey(0);
 return 0;
}
```
Here we use opencv to read a color image, convert it into gray-scale, save it in
a file and also display both the images. For this sort of code to be able to run
succesfully, you need the following:


| Tool/OS | Windows | Linux | Mac |
| --- | --- | --- | --- |
| Compiler | Visual-Studio | gcc | gcc/clang |
| GLUT | freeglut | " | " |
| OpenCV | " | " | " |
| CUDA | " | " | " |
| git | github-desktop | git | git |

The tutorials on how to get them up and running are available widely. All you
need to do is a default installation without any tricks.


Building code
---------------

Once the code is written, it needs to be compiled and run as an executable.
Different operating systems require executables in different ways and 'cmake'
provides a nice cross-platform way to build these executables from the same
source code. 

All you need is a simple CMake template that looks the following way:

```cmake
cmake_minimum_required(VERSION 2.8)
project( MyCVProject )

option( WITH_CUDA "CUDA Enabled" OFF)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package( OpenCV REQUIRED )
find_package( CUDA )

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${OpenCV_INCLUDE_DIRS})


if(WITH_CUDA)
  if(NOT CUDA_FOUND)
    message(FATAL_ERROR "Please install CUDA and make it available for Cmake
      before compiling the code with the WITH_CUDA flag")
  endif ()
endif ()

if(WITH_CUDA)
  cuda_add_executable( DisplayImage DisplayImage.cpp)
  target_link_libraries(DisplayImage ${OpenCV_LIBS})
else ()
  add_executable( DisplayImage DisplayImage.cpp)
  target_link_libraries( DisplayImage ${OpenCV_LIBS})
endif ()
```

This needs to be placed in a file name 'CMakeLists.txt' along with the source.
Using the cmake system, we can generate further build files that are dependent
on the OS. 

| Windows | Linux | Mac |
| --- | --- | --- |
| vcproj | Makefile | Makefile |

Then, you can use the build files to further build using the compilers mentioned
above to make the executable required to run the program. The main advantage of
using cmake system is that all the dependencies on libraries are resolved
using the default installations. This is the main reason that the code becomes
portable and easy to distribute.

Versioning of code
------------------

A lot of programming works by developing through stages. It is definitely worth
it to save these stages as they are. This is where a versioning system comes
very handy. There are several possibilites, but 'git' is my favorite. Also,
Github provides an amazing free service if you don't mind keeping the code
opensource. 

Once you create a repository on github, you can follow the simple instructions
there to set it up on your local machine. The  

