# HDCS GitHub Organization Structure

This repository is the umbrella blueprint for the proposed **Hago Drone Consulting Services** GitHub organization.

## Core Flight Software

| Repository | Purpose |
| --- | --- |
| `hdcs-flight-controller-sdk` | Flight controller abstractions, board support packages, and firmware integration contracts |
| `hdcs-flight-stack` | Core autopilot and flight stack implementation |
| `hdcs-mission-planner` | Mission authoring, constraints, and route optimization |
| `hdcs-ground-control-station` | Operator UI, fleet supervision, and mission monitoring |
| `hdcs-telemetry-system` | Telemetry ingestion, persistence, and replay |
| `hdcs-navigation-engine` | Estimation, filtering, and navigation services |
| `hdcs-guidance-algorithms` | Guidance, control, and path-following algorithms |
| `hdcs-flight-dynamics` | Vehicle models and dynamics libraries |
| `hdcs-autopilot-sdk` | Shared autopilot extension SDK |
| `hdcs-dronecan` | DroneCAN transport and device integration library |
| `hdcs-mavlink` | MAVLink message contracts and tooling |
| `hdcs-px4-interface` | PX4 bridge and adapter services |
| `hdcs-ardupilot-interface` | ArduPilot bridge and adapter services |

## Intelligence and Vision

| Repository | Purpose |
| --- | --- |
| `hdcs-ai` | Detection, tracking, SLAM, path planning, landing, takeoff, swarming, and reinforcement learning |
| `hdcs-computer-vision` | Calibration, stitching, 3D reconstruction, stereo, optical flow, thermal, and multispectral processing |

## Navigation, Mapping, and Planning

| Repository | Purpose |
| --- | --- |
| `hdcs-navigation` | GPS, RTK, PPK, INS, IMU fusion, EKF, UKF, particle filters, and GPS-denied navigation |
| `hdcs-mapping` | Orthomosaic, DEM, DSM, point cloud, LiDAR, photogrammetry, and GIS exports |
| `hdcs-mission-services` | Geofencing, no-fly zones, terrain following, replanning, return-to-home, and emergency landing |

## Swarm and Simulation

| Repository | Purpose |
| --- | --- |
| `hdcs-swarm` | Mesh networking, distributed planning, leader election, consensus, and task allocation |
| `hdcs-simulation` | Gazebo, AirSim, Unreal, Unity, PX4 SITL, ArduPilot SITL, and digital twin integration |

## Shared Platform Repositories

| Repository | Purpose |
| --- | --- |
| `hdcs-api-contracts` | Shared REST, gRPC, MQTT, MAVLink, DroneCAN, and ROS2 contracts |
| `hdcs-platform-ops` | Docker, Kubernetes, observability, supply chain, and deployment automation |
| `hdcs-docs` | End-user, operator, developer, and systems documentation |
