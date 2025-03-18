It is a single file which contains the code about AI VIRTUAL MOUSE

AI VIRTUAL MOUSE :-
------------------

A hands-free way to control your computer using AI and computer vision technologies!

PROJECT OVERVIEW :-
-------------------

The AI Virtual Mouse is an innovative application that allows users to interact with their computer without any physical hardware. Powered by computer vision techniques and machine learning algorithms, it utilizes a webcam to detect and track hand gestures, which are translated into mouse movements and actions like clicking, scrolling, and dragging.

FEATURES :-
------------

-> Real-time hand gesture recognition.
-> Control mouse movements with hand positions.
-> Click and scroll using predefined hand gestures.
-> User-friendly and hardware-independent (only a webcam is required).
-> Highly customizable for different gestures.

TECHNOLOGIES USED:-
------------------

-> Programming Language: Python
-> Libraries and Frameworks:
      - OpenCV (for computer vision tasks)
      - MediaPipe (for hand tracking)
      - PyAutoGUI (for simulating mouse events).

EXPLANATION OF ABOVE CODE :-
---------------------------

1. Importing Libraries
   ...................
  The project begins by importing the essential libraries that enable the functionalities:
  OpenCV: Used for accessing the webcam, processing frames, and displaying the output.
  MediaPipe: Provides robust hand-tracking features to detect and analyze hand gestures in real-time.
  PyAutoGUI: Allows the program to simulate mouse movements and actions on the computer.

2. Initializing Components
   ......................
  Next, the key components are initialized:
  MediaPipe Hand Solution: This provides pre-trained models to detect hands and identify 21 landmark points on each hand (e.g., fingertips, knuckles).
  OpenCV Video Capture: The cv2.VideoCapture(0) function is used to access the webcam and capture video frames in real-time.

3. Video Frame Processing
   ......................
  The program captures video from the webcam frame by frame. Each frame is:
  Converted to RGB: MediaPipe expects input images in RGB format, so frames are converted from BGR (default format in OpenCV) to RGB.
  Analyzed for Hands: The processed frame is passed to MediaPipe's hand detection model, which identifies whether hands are present and maps their landmarks.
  This real-time processing enables dynamic interaction as the user moves their hand.

4. Detecting Hand Landmarks
   ........................
  When a hand is detected, the program identifies its landmarks (specific points on the hand like fingertips and the base of fingers). The coordinates of these landmarks are normalized (values between 0 and 1) and are then converted to pixel values based on the webcam frame's size.
    For instance:
    The index fingertip is often used to move the mouse cursor.
    The positions of multiple landmarks are analyzed to detect gestures (e.g., open palm or a pinching motion).
    Landmark data is the foundation for interpreting user gestures.

5. Gesture Recognition
   ...................
  Custom logic is implemented to map hand gestures to specific mouse actions. Commonly:
  Open Palm (All Fingers Extended): This gesture moves the mouse cursor to match the position of the index fingertip.
  Closed Fist: Detected when all fingers are curled; it simulates a left mouse click.
  Pinch Gesture (Thumb and Index Finger Close): Used to initiate dragging or scrolling actions.
  This step involves comparing distances and relationships between landmark points to identify gestures accurately.

6. Simulating Mouse Actions
  .......................
  Once a gesture is recognized, the corresponding mouse action is executed using PyAutoGUI. Common actions include:
  Moving the Cursor: pyautogui.moveTo(x, y) shifts the cursor to the specified screen coordinates.
  Clicking: pyautogui.click() simulates a left-click.
  Scrolling: pyautogui.scroll(amount) scrolls the screen vertically based on the specified amount.
  This integration connects gesture recognition to actual system interactions, making the program functional as a virtual mouse.

7. Displaying Visual Feedback
   ...........................
  To make the program user-friendly, visual feedback is provided:
  The webcam feed is displayed with annotations (e.g., circles or lines) indicating the detected hand landmarks.
  Text or shapes may highlight recognized gestures, giving real-time feedback to the user.
  For example:
  The position of the index fingertip is marked to show where the mouse cursor is being moved.
  This feature helps users understand how their gestures are being interpreted by the system.

8. Cleanup and Exit
   ................
  When the user closes the program (e.g., by pressing a specific key like q), resources are released:
  The webcam is closed using cap.release().
  All OpenCV windows are destroyed with cv2.destroyAllWindows().
  This ensures that the system resources are freed, preventing any performance issues.

ML MODEL:-
-----------

It uses ML models like CNN(Convolution Neural Network)+Regressions(Continous output)+Classification.
