# kinectToPly #

## About ##

Quickly and easily convert a kinect point cloud to a PLY file which can be loaded and viewed using [MeshLab](http://meshlab.sourceforge.net/) or other such programs.

The depth data can optionally have a bilateral filter applied to it, and a rotation and position can be specified which will transform the resulting point cloud.

## Install and set-up ##

    git clone https://github.com/bponsler/kinectToPly.git
    cd kinectToPly
    ./kinectToPly.py

## Usage ##

    Usage: Syntax: kinectToPly.py [output PLY filename] (options)

    Options:
      -h, --help     show this help message and exit
      --bilateral    apply a bilateral filter to the depth data
      --x=X          x position (meters)
      --y=Y          y position (meters)
      --theta=THETA  rotation value (degrees)

## Example ##

Save an unfiltered scan:

    ./kinectToPly.py /tmp/test.ply
    
Save a bilateraly filtered scan:

    ./kinectToPly.py /tmp/test.ply --bilateral
    
Save a scan at a different position and orientation (left 10 centimeters, and rotated counterclockwise 15 degrees):

    ./kinectToPly.py /tmp/test.ply --x=0.0 --y=0.1 --theta=15
    
## Coordinate system ##

The kinect's coordinate system is as follows (note: directions are from the perspective of the kinect):

    Positive X axis forward
    Positive Y axis to the left
    Positive Z axis to the sky
    Positive rotation is counterclockwise
