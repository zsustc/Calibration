**1. Calibration-of-a-C-arm-x-ray-device-Winter-school**
  Authors: Shuai Zhang


**2. Prerequisites**
  We have tested the code in Ubuntu 18.04, but it should be easy to compile in other platforms.

  OpenCV
  We use OpenCV to manipulate images and features. Dowload and install instructions can be found at: http://opencv.org. Required 3.2.0.

**3. Building DefSLAM library and examples**
  Clone the repository:

  git clone https://github.com/zsustc/Calibration-of-a-C-arm-x-ray-device-Winter-school.git
  Execute:

  mkdir build
  cd build
  cmake .. 
  make

  This will create the executables x_ray_calibration and x_ray_calibration in the current folder.

**4. Datasets**
  The original images captured from the C-arm device can be found in the folder "original_images_uncropped", the size is 1280*1024;
  The cropped images can be found in the folder "uncalibrated", the size is 1024*1024.
  You should use the cropped images since the original images contain extra border illustrating some patient related information.
