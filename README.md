## Face Recognition Toolkit

Small Windows-friendly demo project with two webcam utilities:
- `face_recognition_app.py`: live face recognition against known photos.
- `Face_Mesh_Detection.py`: Mediapipe face mesh overlay for up to 3 faces.

### What you need
- Python 3.9+ recommended
- Webcam
- Packages: `opencv-python`, `mediapipe`, `face_recognition` (brings `dlib`)

Install dependencies:
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt  # if you add one
# or directly
pip install opencv-python mediapipe face_recognition
```

### Files
- `face_recognition_app.py` – loads reference photos and labels faces in a live stream.
- `Face_Mesh_Detection.py` – draws Mediapipe mesh contours in real time.
- `person2.jpg`, `person3.jpg` – sample reference images (replace with your own).

### Running the face recognition demo
```bash
python face_recognition_app.py
```
Behavior:
- Starts the default webcam.
- Detects faces, encodes them, and compares to the known encodings list.
- Draws a red box and label for the first matching known face; otherwise shows "Unknown".
- Press `q` to exit.

Customize known faces:
1) Add your own JPG/PNG files beside the script.  
2) In `face_recognition_app.py`, change the `load_image_file` paths and update `known_face_names`.  
3) Restart the script.

### Running the face mesh demo
```bash
python Face_Mesh_Detection.py
```
- Opens the webcam and overlays Mediapipe face mesh contours (up to 3 faces).
- Press `q` to exit.

### Notes & troubleshooting
- On Windows, `face_recognition` wheels bundle `dlib`; if install fails, ensure you have a C++ build toolchain or use a Python version with available wheels.
- If the webcam will not open, close other apps using it and check privacy settings.
- Performance depends on camera resolution; lower resolution may improve FPS.

