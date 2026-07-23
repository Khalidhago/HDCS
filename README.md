# Hago Drone Consulting Services (HDCS)

Enterprise-oriented GitHub ecosystem blueprint for UAV/UAS systems engineering, autonomy, robotics, AI/computer vision, and industrial drone workflows.

## Mission

Build a technically credible, safety-aware, and reproducible open engineering portfolio for:

- UAV/UAS systems architecture
- Autonomous mission systems
- ROS 2 + PX4/ArduPilot + MAVLink integrations
- Edge AI and aerial computer vision
- Remote sensing and industrial inspection analytics

## Repository Role

This repository is the **ecosystem hub** for HDCS.  
It defines standards, architecture direction, maturity model, and portfolio roadmap.

## Current Maturity

- **Repository maturity:** Level 2 — Functional
- **Intent:** Progress to Level 4 for governance/documentation quality and Level 5 as a reference architecture hub
- **Status labels:** Every linked project should explicitly state Idea / Prototype / Functional / Engineered / Production-Ready / Reference

## Ecosystem Domains

1. UAV/UAS Systems
2. Autonomy and Robotics
3. AI and Computer Vision
4. Remote Sensing and GIS
5. Industrial Drone Applications
6. Software Engineering and DevSecOps
7. Research and Education

## Key Documents

- [Target Repository Architecture](docs/TARGET_REPOSITORY_ARCHITECTURE.md)
- [Repository Maturity Model](docs/REPOSITORY_MATURITY_MODEL.md)
- [12-Month Roadmap](docs/ROADMAP_12_MONTHS.md)
- [Contributing Guide](CONTRIBUTING.md)
- [Security Policy](SECURITY.md)

## Portfolio Governance Baseline

- Standardized README structures and project templates
- Explicit maturity labeling
- Reproducibility-first setup guidance
- Security reporting policy and dependency update policy
- Non-destructive evolution (archive/private decisions require explicit approval)

## Safety and Integrity Principles

- Flight-critical control remains on certified/appropriate flight-control stacks
- AI subsystems are non-flight-critical unless explicitly engineered and validated for that role
- Claims must be defensible, verifiable, and supported by artifacts

## Next Phase Priorities

1. Align profile identity and pinned repositories to HDCS domains
2. Promote flagship repos with clear architecture docs and CI quality gates
3. Standardize governance and security files across all active repositories
4. Build high-value reference projects with testable outputs