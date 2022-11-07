# cv-midterm (Shounak Ghosh)
All code in relation to my Fall 2022 Computer Vision midterm project.
## Prompt 1
Was tasked with creating an object detection pipeline that detects blue armor plates
and displays bounding boxes and depth on a live video feed using OpenCV.

### Design Decisions
Created a Capture class to ..
Created a ColorDetection class to ..

## Prompt 2
Was tasked with displaying the horizontal and vertical angle offset from the center of a detection. The camera resolution/FOV was used for the x and y axis to determine the respective offsets.

### Design Decisions


## Prompt 3 (SystemD)
Was tasked with creating a SystemD service daemon that runs the object detection pipeline on boot. The service file loads PyTorch, required CV libraries, and runs the object detection pipeline inside a virtual environment. The torch version is printed to the system log.

### Design Decisions

