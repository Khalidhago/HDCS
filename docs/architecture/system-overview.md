# System Overview

## Purpose

Define the baseline end-to-end UAV/UAS system architecture used by HAGO DRONE CONSULTING SERVICES for engineering design, integration, simulation, and validation.

## System-of-Systems View

1. **Air Vehicle Segment**
   - Airframe, propulsion, power, onboard sensing, payloads
2. **Autopilot and Control Segment**
   - Flight controller, PX4/ArduPilot stack, control loops, failsafes
3. **Companion Compute and Robotics Segment**
   - Linux companion computer, ROS 2 nodes, mission services
4. **Perception and AI Segment**
   - Vision pipelines, model inference, target/state understanding
5. **Ground Segment**
   - Ground control station, telemetry, operator interfaces
6. **Cloud and Data Segment**
   - Data ingestion, storage, analytics, reporting integrations

## Canonical Data and Control Flow

```text
Sensor Streams → State Estimation → Flight Control → MAVLink Telemetry/Commands
      ↓                                   ↑
 Perception/AI → Autonomy Decisions → Mission Logic → Operator Oversight
      ↓
 Mission Data Pipeline → Analytics/Intelligence
```

## Assumptions

- Safety-critical flight stabilization remains in autopilot domain.
- Companion computer autonomy is constrained by explicit guardrails.
- Communications can degrade; fail-safe behaviors must be deterministic.
- Simulation is required before uncontrolled physical flight trials.

## Risks

- Interface ambiguity between autopilot and companion stack
- Over-trust in AI inference under edge conditions
- Unbounded mission logic causing unsafe actuation requests
- Telemetry loss causing command/awareness mismatch

## Alternatives Considered

- Fully centralized autonomy in cloud (rejected: latency and link-risk)
- Minimal edge autonomy with strict human-in-loop (viable for early ops)
- Hybrid autonomy with bounded onboard decision-making (selected baseline)

## Measurable Success Criteria

- Architecture docs updated per release and traceable to changes
- Defined interfaces for all critical subsystem handoffs
- Simulation-first validation evidence for autonomous features
- Clear declaration of maturity state for each subsystem
