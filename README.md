# 🖐️ 3D Hand Tracking - Cultivation Cube & 2D Screen Mask

A real-time interactive WebGL application combining **MediaPipe Hands** and **Three.js**. This project tracks hand gestures using a webcam to project dynamic 3D objects, visual aura effects, and custom fragment shader screen masks in real-time.

---

## ✨ Features

- **Dual Interaction Modes**:
  - **3D Cultivation Cube Mode**: Triggers when $\ge 4$ fingers are detected on either hand. Spawns a rotating, glowing 3D cube positioned dynamically between both hands with connecting energy aura lines.
  - **2D Mask / Ribbon Mode**: Activates during standard gesture conditions, generating dynamic planar quads or ribbon meshes connecting fingertips and thumbs with custom shader filters.
- **Custom GLSL Fragment Shader Filters**:
  - Invert (Negative)
  - Grayscale
  - Sepia
  - Normal (Pass-through)
- **Hysteresis & Anti-Flicker**: Built-in frame debounce counter ensures smooth transitions between 2D and 3D modes.
- **Dynamic Camera & Aspect Ratio Scaling**: Auto-calculates field-of-view (FOV) and normalizes coordinate spaces across desktop and mobile aspect ratios.
- **Real-Time Controls**: Sleek UI panel for camera switching, filter selection, and accent color customization.

---

## 🛠️ Tech Stack

- **HTML5 & CSS3**: Custom modern dark theme UI using Inter typography.
- **JavaScript (ES6+)**
- **[Three.js](https://threejs.org/)** (r128): 3D rendering engine, materials, custom shaders, and geometry buffers.
- **[MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands.html)**: Real-time hand landmark detection.
- **GLSL**: Custom vertex and fragment shaders for video stream processing.

---

## 🚀 Getting Started

Since all dependencies are loaded via CDN, no complex build steps or node module installations are required.

### Prerequisites

- A modern web browser with **WebGL** and **WebRTC/Camera** permission support (Chrome, Edge, Firefox, Safari).
- A local HTTP server (required for accessing webcam stream securely over `localhost` or `https`).

### Running Locally

1. **Clone the repository**:
   ```bash
   git clone [https://github.com/FIQTOR/3d-hand-tracking.git](https://github.com/FIQTOR/3d-hand-tracking.git)
   cd 3d-hand-tracking

```

2. **Serve the directory**:
Using Python:
```bash
python -m http.server 8000

```


Or using Node.js `serve`:
```bash
npx serve .

```


3. **Open in Browser**:
Navigate to `http://localhost:8000` and allow camera permissions.

---

## 🎛️ How It Works

1. **Camera Initialization**: The application requests media permissions and queries available video input devices.
2. **Gesture Recognition**: MediaPipe processes each video frame, extracting 21 3D hand landmarks per hand.
3. **Finger Counting Algorithm**: Evaluates tip-to-PIP joint relative positions to determine open fingers.
4. **Coordinate Transformation**: Unprojects normalized 2D camera coordinates into 3D world space matching the camera's FOV and aspect ratio.
5. **Shader Processing**: Pass-through GLSL shader handles mirror correction, aspect ratio scale fitting, and real-time color filters.

---

## 👤 Author

**FIQTOR**

* Website: [fiqtor.com](https://fiqtor.com)
* GitHub: [@FIQTOR](https://github.com/FIQTOR)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

```
