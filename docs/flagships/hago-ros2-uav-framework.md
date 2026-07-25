# Flagship Specification: hago-ros2-uav-framework

## Status

`concept`

## One-Sentence Technical Description

ROS 2-based UAV software framework for modular mission services, perception pipelines, autonomy orchestration, and deterministic integration with PX4/MAVLink systems.

## Mission Statement

Provide a maintainable, testable, and safety-aware ROS 2 application framework that accelerates UAV feature development while preserving clear boundaries between flight-critical controls and higher-level mission intelligence.

## Engineering Reason

- Standardize ROS 2 node architecture, interfaces, and QoS for UAV workloads.
- Improve reuse across perception, mission logic, and telemetry services.
- Reduce integration risk between autopilot, companion compute, and mission applications.

## Assumptions

- ROS 2 DDS transport can satisfy target mission-latency and reliability constraints.
- Flight-critical control remains in PX4/autopilot domain.
- Time synchronization and TF2 frame integrity are managed as first-class requirements.

## Risks

- QoS misconfiguration causing dropped or stale mission-critical data
- Node coupling and dependency sprawl reducing maintainability
- Frame/timestamp inconsistencies causing autonomy decision errors
- Resource contention on edge compute platforms

## Alternatives Considered

1. Monolithic mission process without ROS 2 modularity  
   - Rejected for scalability and maintainability limitations.
2. Custom middleware instead of ROS 2/DDS  
   - Rejected due to higher engineering overhead and reduced ecosystem leverage.
3. Modular ROS 2 framework with explicit interface contracts  
   - Selected baseline.

## Measurable Success Criteria

- Versioned message/service contracts for key subsystem interfaces
- Deterministic node graph startup and health monitoring
- Reproducible simulation integration with PX4 SITL scenarios
- Regression suite covering nominal and degraded communication conditions

## Proposed Repository Structure

```text
hago-ros2-uav-framework/
  docs/
    architecture.md
    node-graph.md
    interfaces.md
    qos-profiles.md
    tf2-conventions.md
    validation-plan.md
    limitations.md
  packages/
    mission_orchestrator/
    telemetry_bridge/
    perception_adapter/
    autonomy_supervisor/
    system_health/
  msgs/
  srv/
  launch/
  configs/
    qos/
    runtime/
  tests/
    unit/
    integration/
    simulation/
```

## Architecture Boundaries

- **Flight-critical boundary:** commands to flight stack are bounded and audited.
- **Middleware boundary:** ROS 2 topics/services/actions must use versioned contracts.
- **Perception boundary:** confidence and staleness must be explicit in interfaces.
- **Mission boundary:** autonomy decisions pass through safety and policy gates.

## Validation Gates

1. Static/interface checks for message contract compliance
2. Unit tests per package for core logic
3. Integration tests for inter-node communication and QoS behavior
4. SITL-linked simulation tests for mission scenarios
5. Fault/degraded-mode tests (message delays, dropouts, stale transforms)
6. Controlled ground validation readiness checklist

## Maturity Policy for this Flagship

- `concept`: architecture, contracts, and validation plan defined
- `prototype`: core packages and SITL integration baseline available
- `ground-tested`: controlled bench/ground evidence available
- `flight-tested`: controlled flight integration evidence available
- `production-candidate`: repeatable validation with documented limitations and governance

No maturity stage may be claimed without reproducible evidence.
