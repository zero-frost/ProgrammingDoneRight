Introduction
============

This guide aims to give the reader the knowledge to be able to use OpenCV to solve FRC vision tasks. But more importantly, this guides hopes the reader develops an understanding of the computer vision algorithms that OpenCV provides.

Along with theory, this series of pages will also give the appropriate OpenCV code in C++, Java, as well as Python to provide a grounding to the theory. While the math may get complex at times, we highly suggest you try your best to understand it as we want you to have an understanding of the algorithms themself, not just an understanding of how to call a function.

Data Structures
---------------

A data structure is a programming term that describes the format for organizing and storing data. In computer vision, the type of data we care about are images and points. While there are other data structures within OpenCV, we will cover those as they come up so this section won't be too long.

Images
~~~~~~

The core of computer vision is the analysis of images, thus making the problem of how to efficiently encode images for programming is an essential one. Unfortunately, OpenCV is not consistent across its languages, so feel free to read about the language you are interested in using. 

Generally, the images are 8 bit, meaning that the pixels take a value in the range [0, 255] where 255 is white and 0 is black, but OpenCV does not limit the user to 8 bit images. For instance, the Microsoft Kinect's depth camera produces a 16 bit image.

What is color for OpenCV? In OpenCV, that means that the image has 3 channels, where each channel represents a color. Again, OpenCV does not limit the user to 1 channel (grayscale) or 3 channel (RBG or HSV) images, they can construct 6 channel images if they wish, however that has no practical application to FRC, so shall restrict our images to single channel or 3 channels. 

:math:`\left( \begin{array}{ccc} 39 & 230 & 0 \\ 205 & 79 & 255 \\ 15 & 114 & 165 \end{array} \right)`

C++
^^^

OpenCV's C++ binding encodes images as matrices, where each element in the matrix directly encodes for the pixel value at that particular index.


.. code-block:: ruby

   // creates empty matrices
   cv::Mat A, C;

   // Copy constructor
   cv::Mat B(A);

   // Assignment operator
   C = A;

Java
^^^^

Java's bindings also utilize matrices to encode images, however, as is explained later on, it is a bit trickier to display images.

.. code-block:: ruby

   // allocates memory for a new matrix
   Mat frame = new Mat();

Python
^^^^^^

The Python binding for OpenCV utilizes numpy to handle the heavy lifting of storing and operating on images as numpy is a highly optimized library specifically designed for fast computations. More specifically, the numpy.array is used to store images. This being said, python is not a user specified type casted language, so it is difficult to illustrate how to declare a np.array. While one can create a np.array of size 0, there is no application of that.


Points
~~~~~~

Points in OpenCV are indentical to what you learned in your geometry class. They take the form (x,y), where x and y denote the location in an image, and the origin is the top left corner, positive x is to the right and positive y is down, as is common across computer vision libraries.

.. tabs::

   .. code-tab:: java

       Point pt;
       pt.x = 10;
       pt.y = 8; 
       Point pt2 = new Point(10,8);
       
   .. code-tab:: c++

       Point pt;
       pt.x = 10;
       pt.y = 8; 
       Point pt2 =  Point(10, 8);

   .. code-tab:: py

       #Python uses tuples
       (5, 10)


The Basics
----------

The following few sections will let you get started with OpenCV in the language of your choosing. 

Reading an image from a file
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

While reading images into memory isn't terribly useful for FRC, it is useful for debugging purposes.

.. tabs::

   .. code-tab:: java

        Mat img = Highgui.imread("image.png", Highgui.CV_LOAD_IMAGE_GRAYSCALE);
       
   .. code-tab:: c++

       // 1 denotes to load it as a color image
       img = imread("/home/faust/Documents/vision2013/boilerraw.jpg", 1); 

   .. code-tab:: py

      # 0 denotes to load the image as grayscale
      img = cv2.imread('picture.jpg',0)


Saving an image to a file
~~~~~~~~~~~~~~~~~~~~~~~~~

It is recommended that you save an image every so often for debugging purposes. However, take note that this is a time expensive operation and it is not necessary to do on every frame, one frame a second should be enough. 

.. tabs::

   .. code-tab:: java

        Imgcodecs.imwrite("picture.png",img);
       
   .. code-tab:: c++

       imwrite("picture.png", img)   

   .. code-tab:: py

       cv2.imwrite('picture.png',img)


Getting an image from a usb camera
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Note the 0 in the capture commands. This denotes the first camera the computer recognizes. If you have a webcam, it will default to that. If using multiple cameras, it is best practice to plug them in in the order that you are getting them in your program every time you restart the computer. 

.. tabs::

   .. code-tab:: java

        VideoCapture camera = new VideoCapture(0);
        Mat frame = new Mat();
        camera.read(frame); 
	//use frame for image processing from here
       
   .. code-tab:: c++

	VideoCapture cam;
	Mat image;
	cam.open(0);
	cam >> image;	   

   .. code-tab:: py

       cap = cv2.VideoCapture(0)
       ret, frame = cap.read()
       # use frame for image processing from here
