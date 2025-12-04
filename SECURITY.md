# Security Policy

This repository provides containerization, orchestration, and edge deployment tooling
around the upstream Yawcam-AI project. While this repo does not include compiled model
binaries or proprietary code from upstream, operational security and responsible
deployment practices still apply.

## Supported Versions

The following build paths are intended for regular security awareness and maintenance:

| Variant | Support Status       |
|--------|-----------------------|
| CPU-only build (Ubuntu base) | ✔ Supported |
| GPU-enabled CUDA build       | ✔ Supported |
| Alpine GLIBC hybrid build    | ⚠ Experimental |
| Distroless / minimal images  | ⚠ Future consideration |

Security fixes and operational updates will be applied to supported variants only.

---

## Reporting Vulnerabilities

If you discover:

- Container escape vectors
- Misconfigured permissions
- Privilege elevation risks
- Network exposure issues
- Credential persistence weaknesses

> Please report privately rather than as a public issue.

**Private Reporting Contact:**  
devprincekumar (GitHub profile DM) or Email

A response will typically be provided within **72 hours**.

---

## Responsible Disclosure

Please do not:

- Publish exploit details before we triage and confirm
- Commit PoCs directly to the repo
- Submit issues demonstrating access to your private environments

We will:

✔ acknowledge researcher credit  
✔ document fixes  
✔ ship updated Dockerfiles / compose files where needed  

---

## Security Scope Clarification

This project does NOT modify or publish Yawcam-AI internal logic.
It *packages* and *orchestrates* runtime execution.

⚠ Therefore, vulnerabilities affecting:

- Java runtime
- FFmpeg / CVE risks
- YOLO inference frameworks
- Spring Boot or embedded DB

…must also be disclosed upstream to the original project:

➡ https://github.com/yawcam/yawcam-ai

We recommend reporting directly to both maintainers when in doubt.

---

## Secure Usage Guidelines

To reduce attack surface:

✔ Prefer volume-mapped persistent storage vs container-internal storage  
✔ Run as non-root where possible (future hardening planned)  
✔ If exposing UI remotely, front it behind reverse proxy authentication  
✔ Disable or restrict event-based script execution hooks if unneeded  
✔ On GPU systems, ensure NVIDIA runtime is patched  

---

## Long-term Hardening Roadmap

- Non-root container builds
- Distroless minimal runtime
- Optional reverse-proxy authentication profile
- Signature validation for downloaded model files

Security contributions are highly welcome.
