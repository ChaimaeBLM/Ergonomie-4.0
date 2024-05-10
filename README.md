# Real-time Object Detection and Posture Evaluation using YOLOv8 and Streamlit

"Ergonomy 4.0" is an innovative academic project that harnesses the capabilities of computer vision to enhance industrial safety and efficiency. In the demanding environment of welding operations, ensuring the proper use of Personal Protective Equipment (PPE) and maintaining correct posture are critical for operator safety. This project specifically aims to develop a computer vision system capable of real-time detection of PPE compliance and posture evaluation.

By integrating advanced image processing techniques, the system will continuously monitor welding operators to check for the proper use of helmets, gloves, and other protective gear, and assess their posture during operations. This dual capability aims to significantly reduce the risk of injuries and long-term health problems associated with poor ergonomics and inadequate safety gear usage.

Our goal is not only to create a tool that improves workplace safety but also to provide a framework that can be adapted to other industrial settings where safety and ergonomics are of paramount importance. This project represents a crucial step towards embedding intelligent safety solutions in industrial operations, aligning with the principles of Industry 4.0 to create smarter, safer workplaces.

## Demo Pics

### Home page

<img src="https://github.com/ChaimaeBLM/Ergonomie-4.0/blob/main/images/ergonomie4.0Interface.png" >

## Technologies Stack
This project was successfully implemented using cutting-edge technologies in computer vision and web application development.
### Streamlit:
Streamlit is an open-source Python library designed to make it easy for developers to create and share beautiful, custom web apps for machine learning and data science. It allows users to turn data scripts into shareable web applications quickly and with minimal code.
### MediaPipe:
MediaPipe is an open-source framework created by Google for building multimodal (video, audio, any time-series data) applied machine learning pipelines. It offers developers pre-built modules that include model solutions for tasks like face detection, hand tracking, and object detection, facilitating the rapid development of prototypes and applications on both desktop and mobile platforms.
### YOLOv8:
YOLOv8 (You Only Look Once version 8) is a deep learning model for object detection tasks, which can identify and classify different objects in images or video frames in real-time. It is the eighth iteration of the YOLO series, known for its speed and accuracy in detecting objects by processing the image in a single pass, hence the name "You Only Look Once".
## Requirements

Python 3.6+
YOLOv8
Streamlit
mediapipe
openCV


## Usage

- Run the app with the following command: `streamlit run app.py`
- The app should open in a new browser window.

### ML Model Config

- Select task (Detection)
- Select model confidence
- Use the slider to adjust the confidence threshold (25-100) for the model.

One the model config is done, select a source.

### Detection on images

- The default image with its objects-detected image is displayed on the main page.
- Select a source. (radio button selection `Image`).
- Upload an image by clicking on the "Browse files" button.
- Click the "Detect Objects" button to run the object detection algorithm on the uploaded image with the selected confidence threshold.
- The resulting image with objects detected will be displayed on the page. Click the "Download Image" button to download the image.("If save image to download" is selected)

## Detection in Videos

- Create a folder with name `videos` in the same directory
- Dump your videos in this folder
- In `settings.py` edit the following lines.

```python
# video
VIDEO_DIR = ROOT / 'videos' # After creating the videos folder

# Suppose you have four videos inside videos folder
# Edit the name of video_1, 2, 3, 4 (with the names of your video files) 
VIDEO_1_PATH = VIDEO_DIR / 'video_1.mp4' 
VIDEO_2_PATH = VIDEO_DIR / 'video_2.mp4'
VIDEO_3_PATH = VIDEO_DIR / 'video_3.mp4'
VIDEO_4_PATH = VIDEO_DIR / 'video_4.mp4'

# Edit the same names here also.
VIDEOS_DICT = {
    'video_1': VIDEO_1_PATH,
    'video_2': VIDEO_2_PATH,
    'video_3': VIDEO_3_PATH,
    'video_4': VIDEO_4_PATH,
}

# Your videos will start appearing inside streamlit webapp 'Choose a video'.
```

- Click on `Detect Video Objects` button and the selected task (detection/segmentation) will start on the selected video.

## Acknowledgements

This app is based on the YOLOv8(<https://github.com/ultralytics/ultralytics>) object detection algorithm. The app uses the Streamlit(<https://github.com/streamlit/streamlit>) library for the user interface.



