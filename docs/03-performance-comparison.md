
# Performance Comparison 
## CPU vs GPU Mode
---

## Setup

| Element     | Configuration                |
| ----------- | ---------------------------- |
| RTSP Source | PiStream-Lite @ 720p         |
| Container 1 | CPU-only Ubuntu base         |
| Container 2 | CUDA accelerated             |
| Host        | Intel desktop running Docker |

---

## Metrics

### YOLO inference latency

| Condition     | Avg Per-Frame Latency |
| ------------- | --------------------- |
| CPU container | 140–230 ms            |
| GPU container | 18–35 ms              |

> ~6-10× faster inference under identical load

---

### Host CPU Utilization

| Mode               | CPU %  |
| ------------------ | ------ |
| CPU-only container | 70–95% |
| GPU accelerated    | 17–35% |

---

### GPU Load (CUDA mode)

| Measurement       | Observation                   |
| ----------------- | ----------------------------- |
| GPU usage         | 10%–35% active                |
| Utilization burst | aligned with detection events |

---

### Thermal Outcome (tracked via EdgePulse)

* CPU-only spikes temps more aggressively
* GPU mode maintains cooler host profile while increasing throughput

# Key Interpretation

✔ GPU is **not required**
✔ But becomes a strong multiplier under dense detection loads
✔ Even on CPU-only, system remains functional
✔ The Pi can be added as a remote compute node in future (Jetson deployment stage)

---
