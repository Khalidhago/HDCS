# HDCS Reference Architecture

## Purpose

This repository defines the baseline architecture for a complete open-source drone software ecosystem under **Hago Drone Consulting Services**.

## Layered platform model

### 1. Embedded and Edge Layer

- STM32 and ESP32 firmware components
- Onboard compute profiles for NVIDIA Jetson, Raspberry Pi, and Intel x86
- Hardware abstraction for sensors, payloads, and radios

### 2. Flight and Autonomy Layer

- Flight controller SDK and autopilot SDK
- Flight stack, navigation engine, guidance algorithms, and flight dynamics library
- PX4 and ArduPilot interfaces
- MAVLink and DroneCAN protocol libraries

### 3. Perception and Intelligence Layer

- AI inference services for detection, tracking, SLAM, and collision avoidance
- Computer vision pipelines for calibration, stitching, stereo, thermal, and multispectral analytics
- Path planning and reinforcement learning modules

### 4. Mission and Swarm Layer

- Mission planning services for waypoints, geofencing, no-fly zones, terrain following, and return-to-home
- Distributed coordination services for mesh networking, leader election, consensus, and task allocation

### 5. Ground and Cloud Operations Layer

- Ground control station
- Telemetry and observability services
- Mapping and GIS processing services
- Deployment, DevSecOps, and fleet management workflows

## Integration contracts

- **REST API:** external control plane and administrative integration
- **gRPC API:** internal low-latency service-to-service contracts
- **MQTT:** telemetry, events, and lightweight field messaging
- **MAVLink:** autopilot and mission communications
- **DroneCAN:** CAN bus device interoperability
- **ROS2:** robotics middleware bridge for simulation and autonomy

## Plugin model

The ecosystem is designed around replaceable plugins for:

- Autonomy algorithms
- Navigation filters
- Sensor and payload drivers
- Simulation adapters
- Protocol transports
- Deployment profiles

## Quality model

- Unit testing per repository
- Integration testing across API and protocol boundaries
- SITL and HIL validation for flight-critical components
- CI/CD pipelines with linting, testing, artifact generation, and release promotion
- Security scanning, SBOM generation, and signed release artifacts

## Deployment model

- **Local development:** Docker and docker-compose profiles
- **Edge deployment:** containerized services for Jetson, Raspberry Pi, and x86
- **Cloud deployment:** Kubernetes for telemetry, mapping, orchestration, and fleet services
- **Simulation:** PX4 SITL, ArduPilot SITL, Gazebo, AirSim, Unreal Engine, and Unity
