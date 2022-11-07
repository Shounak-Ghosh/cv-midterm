# cv-midterm (Shounak Ghosh)
All code in relation to my Fall 2022 Computer Vision midterm project.
## Prompt 1
The task involved creating an object detection pipeline that detects blue armor plates
and displays bounding boxes and depth on a live video feed using OpenCV.

### Design Decisions
A ColorDetection class was created to determine if a given frame contains more blue area than red. The frame is converted to HSV and red and blue masks are applied respectively. OpenCV's findContours() function is used for each mask. The area of each contour is calculated and the sum of the areas is compared. If the blue area is greater than the red area, the frame is considered to contain blue armor plates.

A Capture class was created to handle the video capture and frame processing. The Capture class contains a ColorDetection object  The Capture class is initialized with a video source. The video source can be a camera or a video file. The Capture class contains a process_frame() method that runs the object detection pipeline on each frame. Bounding boxes are drawn around the detected blue armor plates and the confidence score is displayed. (Depth estimation is not implemented yet.)


## Prompt 2
The task involved displaying the horizontal and vertical angle offset from the center of a detection. The camera resolution/FOV was used for the x and y axis to determine the respective offsets.

### Design Decisions
The DepthCamera class attempted to extract the bounding box coordinates in order to compute angle offsets. However, get_coordinates() was unable to return the bounding box coordinates. This issue needs to be resolved.


## Prompt 3 (SystemD)
The task involved creating a SystemD service daemon that runs the object detection pipeline on boot. The service file loads PyTorch, required CV libraries, and runs the object detection pipeline inside a virtual environment. The torch version is printed to the system log.

### Design Decisions
Followed the instructions on the Google Slides presentation about SystemD. The service file is located in the systemd/ directory. The service file loads the virtual environment and runs the object detection pipeline. The service file is copied to /etc/systemd/system/ and the service is enabled and started. The service is started on boot.


