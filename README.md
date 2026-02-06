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

## IMU vs. Real 6DoF through EdgeTrack

Pen3D is designed around a simple principle: **real 6DoF should come from geometry, not from integration**. An IMU can report angular velocity and acceleration at very high rates, which is useful for low-latency motion, but it cannot directly measure absolute position. As soon as you integrate acceleration to velocity and velocity to position, small sensor biases turn into drift. In practice, an IMU-only device quickly becomes unreliable in stillness: the pose “walks” even when the hand is not moving. Magnetometers can reduce yaw drift, but they introduce sensitivity to local magnetic disturbances and still do not solve absolute position.

EdgeTrack-style outside-in tracking solves the core problem by measuring the device **in world coordinates**. With stereo geometry, HandNode’s markers are observed directly, and a full **6DoF pose** (3D position + 3D orientation) is estimated from **visible marker layout**. This is not a guess based on integrated noise; it is an absolute measurement derived from camera rays, calibration, and deterministic pose estimation (PnP / multi-view constraints). The result is **drift-free stability**, reproducible alignment, and reliable stillness — critical for authoring, CAD-like manipulation, and MoCap workflows where small errors compound into user frustration.

IMU can still be optional as a “fast layer” for prediction, but HandNode intentionally does not depend on it. Instead, it treats **visibility** as the primary design constraint: markers are placed to minimize occlusion and maximize baseline observability, so tracking quality is controlled by physical layout rather than hidden heuristics. This makes HandNode a universal, form-agnostic tool: swap the grip, dial, pen, or handle, keep the marker geometry, and the tracking remains stable and precise.

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


