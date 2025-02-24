# YouTube Hand Gesture Control

Control YouTube video playback using hand gestures captured through your webcam. This Python application uses computer vision and hand tracking to detect finger positions and convert them into keyboard commands for controlling video playback.

## Features

- Real-time hand gesture recognition
- Controls YouTube video playback using simple hand gestures
- Supports 5 different gestures for different controls
- Uses webcam input for gesture detection
- Low latency response

## Gesture Controls

| Gesture (Fingers) | Action |
|------------------|--------|
| 1 finger         | Skip forward (Right arrow) |
| 2 fingers        | Skip backward (Left arrow) |
| 3 fingers        | Volume up (Up arrow) |
| 4 fingers        | Volume down (Down arrow) |
| 5 fingers        | Play/Pause (Spacebar) |

## Prerequisites

Make sure you have the following installed:
```
python 3.7+
opencv-python
mediapipe
pyautogui
```

## Installation

1. Clone this repository or download the source code
2. Install the required packages:
```bash
pip install opencv-python mediapipe pyautogui
```

## Usage

1. Open a YouTube video in your browser
2. Run the script:
```bash
python gesture_control.py
```
3. Position your hand in front of the webcam
4. Use the gestures shown in the table above to control the video playback
5. Press 'ESC' to exit the application

## How It Works

The application uses:
- MediaPipe for hand landmark detection
- OpenCV for webcam capture and image processing
- PyAutoGUI for simulating keyboard inputs

The program:
1. Captures video feed from your webcam
2. Detects hand landmarks using MediaPipe
3. Counts extended fingers based on landmark positions
4. Converts finger counts into corresponding keyboard commands
5. Applies a 0.2-second delay between gestures to prevent accidental triggers

## Technical Details

- The `count_fingers()` function measures the distance between finger landmarks to determine if fingers are extended
- A threshold is calculated dynamically based on hand size in the frame
- The program only detects one hand at a time for consistency
- Video feed is flipped horizontally for more intuitive interaction

## Troubleshooting

If you encounter issues:
1. Ensure your webcam is properly connected and accessible
2. Check that you have sufficient lighting
3. Position your hand clearly in the camera's field of view
4. Make sure no other application is using your webcam

## Dependencies

- OpenCV (`cv2`): For webcam capture and image processing
- MediaPipe (`mediapipe`): For hand tracking and landmark detection
- PyAutoGUI (`pyautogui`): For keyboard control simulation

## Notes

- The application works best in good lighting conditions
- Keep your hand steady for better recognition
- Maintain a reasonable distance from the camera
- The webcam feed window must be active for gesture detection

## License

This project is available under the MIT License. Feel free to modify and distribute as needed.
