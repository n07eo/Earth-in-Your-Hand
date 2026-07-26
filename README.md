#🌍 Earth in Your Hand

A hand-tracking WebGL experiment by Hamaidia Abd el wadoud: control a spinning, zoomable 3D globe using nothing but your webcam and your hands.

Right hand — point your index finger to move the globe around the screen. Make a fist to freeze its spin.
Left hand — push forward to spin the globe. Pinch your thumb and index finger together (with your other three fingers folded) to zoom in and out.

No mouse, no keyboard, no controllers — just you and your camera.

Preview

<img width="1537" height="1023" alt="ChatGPT Image 26 juil  2026, 20_34_15" src="https://github.com/user-attachments/assets/62b7f687-7b92-4be0-99f0-73dfd0956b6f" />

Demo

Open index.html in a browser (see Running locally below) and grant camera access when prompted.

How it works
MediaPipe Hands tracks 21 landmarks per hand in real time from the webcam feed.
Three.js renders a textured, cloud-layered Earth sphere.
Simple physics (easing + friction) smooth out the raw hand-tracking data so the globe moves and spins naturally instead of jittering.

All the logic lives in a single self-contained index.html — no build step, no dependencies to install.

Running locally

Because the page requests webcam access, most browsers require it to be served over http:// or https:// rather than opened directly via file://. Any simple local server works:

bash
# Python
python3 -m http.server 8000

# Node
npx serve .

Then visit http://localhost:8000 (or whatever port your tool prints) and allow camera access when prompted.

Requirements
A webcam
A modern browser with WebGL and getUserMedia support (recent Chrome, Firefox, Edge, or Safari)
Reasonable, even lighting so your hands can be tracked reliably
Tech stack
Library	Purpose
MediaPipe Hands	Hand landmark detection
MediaPipe Camera Utils	Webcam frame capture helper
Three.js r128	3D rendering

All three are loaded from public CDNs, so there's nothing to npm install.

Privacy

All hand tracking runs entirely in your browser. Your webcam feed is never uploaded or sent anywhere — it's processed locally by MediaPipe and immediately discarded.

Author

Made by Hamaidia Abd el wadoud.
