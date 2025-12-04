# Contributing Guide

Thank you for considering contributing to this project!
This repository maintains unofficial containerization and orchestration layers for
Yawcam-AI and forms part of a broader edge computing ecosystem.

We welcome contributions in the following areas:

- Dockerfile improvements  
- GPU runtime tuning  
- EdgePulse integration hooks  
- Documentation / usage guides  
- Testing / benchmarking automation  
- Alpine / distroless builds  

---

## Code of Conduct

Be respectful, constructive and curious.
This project values technical insight over ego.

---

## Contribution Types

### 1. Issues
- Bug reports
- Build failures
- Incorrect version mapping
- Network / volume behavior issues

### 2. Enhancements
- Feature suggestions
- Better docker-compose flows
- Edge deployment compatibility
- System resource optimizations

### 3. PRs (Pull Requests)
We **prefer focused PRs** over giant multi-topic ones.

---

## Before You Submit PRs

### For Dockerfile PRs
- Build locally  
- Verify web UI opens  
- Ensure persistent volume binding works  
- Test on `docker compose up/down` lifecycle  

### For GPU / CUDA PRs
- Confirm container detects CUDA when available  
- Confirm CPU fallback works when GPUs are absent  

### For Docs PRs
- Follow the style of `/docs/`
- Keep README approachable and practical  

---

## Contribution Workflow

1. Fork this repository
2. Create a feature branch:
