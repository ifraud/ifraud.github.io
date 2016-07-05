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
| GLUT | freeglut | - | - |
| OpenCV | - | - | - |
| CUDA | - | - | - |
| git | github-desktop | git | git |

The tutorials on how to get them up and running are available widely. All you
need to do is a default installation without any tricks.
