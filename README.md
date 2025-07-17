# 🌍 Earth — A Realistic 3D Planet with Atmosphere & Stars (Three.js)

This is my second project using **Three.js**, where I built a realistic, rotating 3D model of **Earth**, complete with bump maps, specular highlights, atmospheric glow, clouds, and a starfield background.

It helped me build upon what I learned in my first project while diving deeper into **materials, lighting, texture mapping**, and **custom shader effects**.

<img width="1910" height="964" alt="image" src="https://github.com/user-attachments/assets/bff427b0-58da-4453-8a4a-edcf43958651" />


---

## 🚀 Live Demo

[Demo](https://earth01.netlify.app/)

---

## 🧠 Key Concepts I Learned

This project was a major learning step. Here are the most important concepts I explored and understood:

### 🌐 Advanced Materials & Textures
- **MeshPhongMaterial**: Used for Earth's surface with:
  - `map`: Color texture
  - `specularMap`: Highlights ocean reflections
  - `bumpMap`: Adds terrain depth
- **MeshStandardMaterial**: Used for the **cloud layer**, allowing better lighting interactions with transparency and blending.
- **MeshBasicMaterial**: Used for glowing city lights (non-reactive to light).
- Learned how to **load and layer multiple textures** using `TextureLoader`.

### 🌌 Starfield Generation
- Created a **procedural starfield** using a helper function (`getStarfield`), made up of thousands of small points for a spatial background.

### 🔆 Lighting Techniques
- **DirectionalLight** simulates sunlight and gives the scene strong highlights and shadows.
- Used `ACESFilmicToneMapping` for better color grading and realistic light falloff.

### 🌫️ Fresnel Glow Effect
- Used a custom **Fresnel shader material** (from `getFresnelMat.js`) to simulate a subtle atmospheric glow around Earth.
- Learned about **custom shaders and edge-based glow** via the Fresnel equation.

### 🌥️ Transparent Cloud Layer
- Added a separate mesh for **clouds** using `alphaMap` for transparency, slight rotation difference to simulate atmospheric movement.

### 🔄 Animation and Rotation
- Earth, clouds, city lights, and glow are all set to rotate independently for realism.
- Used `requestAnimationFrame` for smooth animation updates.

### 📐 Grouping and Axial Tilt
- Grouped all Earth components (`earthGroup`) and applied a **23.4° axial tilt** to simulate Earth’s natural orientation.

```js
earthGroup.rotation.z = -23.4 * Math.PI / 180;
