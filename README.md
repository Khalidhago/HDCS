# Hago Drone Consulting Services (HDCS) Open-Source Drone Ecosystem

Welcome to the HDCS master repository. This repository contains the architecture, DevSecOps pipelines, and microservices for a production-ready, modular open-source drone software ecosystem.

## Components

### Core Flight & SDKs
* `hdcs-core-sdk`: Universal API/SDK (C++, Python, Rust, Go) for interfacing with HDCS drones.
* `hdcs-flight-stack`: High-level flight controller interface managing MAVLink and DroneCAN protocols.
* `hdcs-autopilot-bridge`: Abstraction layers for PX4 and ArduPilot integration.
* `hdcs-gcs-core`: Cross-platform Ground Control Station backend.

### AI & Computer Vision
* `hdcs-ai-inference`: Model inference pipelines supporting TensorRT, ONNX, PyTorch, and TensorFlow.
* `hdcs-cv-pipeline`: Computer vision modules for 3D reconstruction, optical flow, and image stitching.
* `hdcs-perception`: ROS2 nodes for Object Detection (YOLO, RT-DETR), Tracking (SAM), and SLAM.

### Navigation & Swarming
* `hdcs-nav-engine`: Sensor fusion (EKF/UKF) blending RTK/PPK GPS, IMU, and visual odometry.
* `hdcs-swarm-mesh`: Mesh networking protocols, distributed mission planning, and leader election consensus algorithms.

### Mapping & Simulation
* `hdcs-mapping`: Photogrammetry tools, DEM/DSM generation, and point cloud (LiDAR) processing.
* `hdcs-mission-planner`: Route planning, geofencing, dynamic replanning, and multi-drone mission generation.
* `hdcs-sim`: Digital twin and SITL (Software In The Loop) simulation bridges for Gazebo, AirSim, and Unreal Engine.

## License
This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for details.
