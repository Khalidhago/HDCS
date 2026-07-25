# Interface Boundaries

## Purpose

Define technical boundaries, ownership, and interface contracts between critical UAV/UAS subsystems.

## Boundary Map

## 1) Sensor Layer ↔ Flight Controller

- **Inputs to FC:** IMU, GNSS/RTK, barometer, magnetometer, optional range sensors
- **Contract:** Time sync, calibration state, health reporting
- **Failure handling:** Invalid sensor states trigger degraded mode or failsafe

## 2) Flight Controller/Autopilot ↔ Companion Computer

- **Interface:** MAVLink over UART/Ethernet/UDP
- **Contract:** Command authority levels, mode control permissions, heartbeat requirements
- **Boundary rule:** Companion cannot bypass core flight safety/failsafe logic

## 3) Companion Computer ↔ ROS 2 Graph

- **Interface:** ROS 2 topics/services/actions
- **Contract:** Message schemas, QoS profiles, timing expectations
- **Boundary rule:** Safety-critical outputs require explicit gating node(s)

## 4) ROS 2 Perception ↔ Autonomy/Mission Logic

- **Interface:** Detection/tracking/state-estimate messages
- **Contract:** Confidence scores, stale-data handling, frame consistency (TF2)
- **Boundary rule:** Low-confidence perception cannot directly trigger irreversible actions

## 5) Vehicle ↔ Ground Control

- **Interface:** Telemetry + command channels
- **Contract:** Command acknowledgment, operator override precedence, audit logs
- **Boundary rule:** Human override paths must remain available for defined mission classes

## 6) Ground/Vehicle ↔ Cloud/Data Platform

- **Interface:** Batch/stream upload APIs
- **Contract:** Data integrity checks, retention policy, access control
- **Boundary rule:** Cloud dependency must not be required for immediate flight safety

## Ownership Model

- **Flight safety owner:** Flight-control/autopilot engineering
- **Autonomy owner:** Robotics + AI engineering with safety constraints
- **Comms owner:** RF/telemetry engineering
- **Data owner:** Platform/data engineering

## Interface Change Control

- Any interface change requires:
  1. Versioned schema/contract update
  2. Backward compatibility assessment
  3. Simulation regression evidence
  4. Updated risk statement
