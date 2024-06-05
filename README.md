# Bicep-Curl-Counter-using-Computer-Vision


## Introduction

The project, the "Bicep Curl Counter using Computer Vision," leverages computer vision and machine learning to track and quantify exercise repetitions accurately. This innovative system employs the Media Pipe library in conjunction with OpenCV to process video input, making it applicable for both real-time live capture and recorded video analysis. The code for the project is written in python. Here, the specific application of this project is counting the number of bi-cep curls done during an exercise and to demonstrate the various uses of the computer vision.


Click <a herf="https://github.com/vamshirayala/Bicep-Curl-Counter-using-Computer-Vision/blob/main/curl_counter.py">here!</a> For the code.

## Working

1. **Initialization**:
   - Import necessary libraries: `cv2` for computer vision tasks, `mediapipe` for pose detection, and `numpy` for numerical operations.
   - Initialize the MediaPipe pose solution for detecting human poses and landmarks.
2. **Video Capture Setup**:
   - Capture video input from the default camera using `cv2.VideoCapture(0)`.
3. **Curl Counter Variables**:
   - Initialize counter variables: `counter` to keep track of the number of curls and `stage` to track the current stage of the curl (up or down).
4. **Angle Calculation Function**:
   - Define a function `calculate_angle(a, b, c)` to calculate the angle at the elbow using the coordinates of the shoulder (a), elbow (b), and wrist (c). The angle is calculated using the arctangent of the differences in coordinates and converting it to degrees.
5. **Pose Detection and Processing**:
   - Within a loop, continuously read frames from the video capture.
   - Convert the frame from BGR to RGB color space, as MediaPipe expects RGB input.
   - Process the frame using the MediaPipe pose detection to get pose landmarks.
6. **Extract Landmarks**:
   - Extract the coordinates of the left shoulder, left elbow, and left wrist from the detected landmarks.
7. **Calculate Angle**:
   - Use the `calculate_angle` function to compute the angle at the left elbow using the extracted landmarks.
8. **Curl Counting Logic**:
   - Display the calculated angle on the frame.
   - Implement the logic to count curls:
     - If the angle is greater than 150 degrees, set the stage to "down".
     - If the angle is less than 50 degrees and the stage was "down", increment the counter and set the stage to "up".
9. **Render Curl Counter and Stage**:
   - Display the count of curls and the current stage on the video frame.
   - Draw pose landmarks and connections on the frame using MediaPipe's drawing utilities.
10. **Display the Processed Frame**:
    - Show the processed frame with the overlayed information using `cv2.imshow`.
11. **Exit Condition**:
    - Exit the loop and release resources when the 'q' key is pressed.
12. **Cleanup**:
    - Release the video capture and close all OpenCV windows.
The code leverages computer vision and pose detection techniques to track the position of key body parts and count the number of bicep curls performed in real-time. This system can be extended to other exercises and applications where tracking specific body movements is required.


Note: Necessary modules like opencv-python and mediapipe should be installed before running the code.
 
## Output

<div align="center">
    <img src="https://github.com/vamshirayala/Bicep-Curl-Counter-using-Computer-Vision/assets/101399344/1d49159f-4565-42e0-8107-2bbcb8b2fc43" alt="Output GIF" width="500"/>
</div>

