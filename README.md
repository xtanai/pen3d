# Pen3D

**Pen3D** is a minimal, professional **3D input device** designed to be tracked by **stereo camera systems** (e.g. EdgeTrack).  
It focuses on **precision, simplicity, and deterministic behavior** for authoring and technical workflows.

---

## Overview

Pen3D is tracked using a **stereo camera setup** and requires only **two small optical markers** for full 6DoF pose estimation.  
This keeps the device lightweight, robust, and easy to manufacture.

---

## Tracking Concept

- **Stereo-camera-based tracking**
- **2 optical markers are sufficient** for position and orientation
- No internal IMU required
- No onboard cameras required
- Deterministic, geometry-based tracking

---

## Input & Interaction

### Minimal Button Mode
- **Single button** for basic interactions
- Optional **third marker** can be mechanically enabled:
  - When inactive: hidden / ignored
  - When active: visible to the stereo system
- Allows simple **mode switching** without electronics

### Extended Input (Optional)
For more advanced input:
- Additional buttons
- Jog dial / hand wheel
- Multi-function controls

These can be easily integrated via:
- **BLE**
- Small **ESP32-S3** module

This keeps the core Pen3D design simple while allowing extensions when needed.

---

## Design Goals

- Minimal electronics
- Low latency
- High precision
- Modular input concept
- Professional workflows (CAD, DCC, VR authoring, R&D)

---

## Roadmap

**Coming soon.**

---

## Status

Early development / prototyping phase.  
Documentation and hardware designs will be published incrementally.


