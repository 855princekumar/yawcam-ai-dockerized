
# Model Replacement & Fine-Tuning Guide

---
## Supported Detector Families

Yawcam-AI supports only:

* YOLOv7
* YOLOv7-tiny
* YOLOv4-tiny

➡ You cannot deploy YOLOv5/8/RT-DETR etc.
➡ You **can retrain and replace** these supported ones.

---

## Default Location

```
/root/.yawcam-ai/models/
```

You can overwrite:

```
*.cfg
*.weights
*.names
```

---

## Procedure

1. Stop container
2. Replace model files in mounted host folder
3. Start container again

---

## When NOT Compatible

If the architecture does not match weights,
the application logs will warn you and disable detection.

---
