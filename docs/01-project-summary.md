
# Project Summary  
## Yawcam-AI Dockerized Edge Pipeline

## Overview

This project packages **Yawcam-AI** into reproducible CPU-only and GPU-enabled containers with:

* persistent storage,
* support for RTSP video analytics,
* YOLO-powered inference,
* automation hooks for event-based processing,
* edge-grade system stability (24/7 operation).

This container becomes part of a three-node edge stack:

1. **PiStream-Lite** — RTSP streaming from camera nodes
2. **Yawcam-AI (this repo)** — inference + recording + automation
3. **EdgePulse** — monitoring, diagnostics & optimization layer

---

## Motivation

Native setup was:

* inconsistent between machines
* fragile under OS differences
* hard to deploy to others

The solution is:

**Infrastructure as Code + Edge System Engineering**
Containerized, repeatable, replicable, and observable.

---

## What This Enables

✔ Plug-and-play video inference on local network
✔ Persisted AI pipeline even after container rebuilds
✔ Runs 24/7 with **EdgePulse-guided optimization**
✔ Works on:

* Windows host
* Linux workstation
* Industrial hardware boxes
* Raspberry Pi acting as the camera source
* Jetson-class devices (future GPU offload)

---

## Key Technologies

| Layer             | Component                           |
| ----------------- | ----------------------------------- |
| Video capture     | PiStream-Lite                       |
| AI inference      | Yawcam-AI YOLO integration          |
| Storage           | Embedded DB + filesystem            |
| Automation        | Email, FTP upload, script execution |
| Ops & Reliability | EdgePulse monitoring framework      |
| Runtime           | Docker / Compose                    |
| Persistence       | Host-bound volumes                  |

---

