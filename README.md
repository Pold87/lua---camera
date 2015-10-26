DEPENDENCIES:
MacOS: Install OpenCV 2.X: http://opencv.willowgarage.com/
Linux: None

All: Torch7 (follow instructions here: www.torch.ch)

Remember for the next time:

I had to use
`#include <opencv/cv.h>`
instead of
`#include <cv.h>`

I could find that via
`sudo find /usr/include -name "highgui.h"`

Instead of forking the repository, a simpler way would have been to add 
`/usr/include/opencv` to my path.

INSTALL:
$ luarocks install camera

STATE:
MacOS: working on all MacOS builds, using OpenCV (wrapper from Jordan Bates)
Linux: working all right, using raw video4linux2 (wrapper from Clement Farabet)

USE:
$ torch
> require 'camera'
> camera.testme()   -- a simple grabber+display
> cam = image.Camera()  -- create the camera grabber
> frame = cam:forward()  -- return the next frame available
> cam:stop() -- release the camera
> image.display(frame)  -- display frame
