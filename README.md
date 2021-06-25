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
  
  "Usage: calibration\n"
        "     -w=<board_width>         # the number of inner corners per one of board dimension\n"
        
        "     -h=<board_height>        # the number of inner corners per another board dimension\n"
        "     [-pt=<pattern>]          # the type of pattern: chessboard or circles' grid\n"
        "     [-n=<number_of_frames>]  # the number of frames to use for calibration\n"
        "                              # (if not specified, it will be set to the number\n"
        "                              #  of board views actually available)\n"
        "     [-d=<delay>]             # a minimum delay in ms between subsequent attempts to capture a next view\n"
        "                              # (used only for video capturing)\n"
        "     [-s=<squareSize>]       # square size in some user-defined units (1 by default)\n"
        "     [-o=<out_camera_params>] # the output filename for intrinsic [and extrinsic] parameters\n"
        "     [-op]                    # write detected feature points\n"
        "     [-oe]                    # write extrinsic parameters\n"
        "     [-zt]                    # assume zero tangential distortion\n"
        "     [-a=<aspectRatio>]      # fix aspect ratio (fx/fy)\n"
        "     [-p]                     # fix the principal point at the center\n"
        "     [-v]                     # flip the captured images around the horizontal axis\n"
        "     [-V]                     # use a video file, and not an image list, uses\n"
        "                              # [input_data] string for the video file name\n"
        "     [-su]                    # show undistorted images after calibration\n"
        "     [input_data]             # input data, one of the following:\n"
        "                              #  - text file with a list of the images of the board\n"
        "                              #    the text file can be generated with imagelist_creator\n"
        "                              #  - name of video file with a video of the board\n"
        "                              # if input_data not specified, a live view from the camera is used\n"

**4. Datasets**
  The original images captured from the C-arm device can be found in the folder "original_images_uncropped", the size is 1280*1024;
  The cropped images can be found in the folder "uncalibrated", the size is 1024*1024.
  You should use the cropped images since the original images contain extra border illustrating some patient related information.
