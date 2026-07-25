# Flagship Specification: hago-uav-simulation-lab

## Status

`concept`

## One-Sentence Technical Description

Simulation-first UAV/UAS systems-engineering platform integrating PX4 SITL, ROS 2, Gazebo, mission logic, and validation workflows before controlled real-world testing.

## Mission Statement

Provide a reproducible environment to design, verify, and de-risk autonomy, mission, and integration features through staged simulation and evidence-based progression to ground and flight testing.

## Engineering Reason

- Reduce safety and integration risk before field deployment.
- Detect interface and autonomy failures early at lower cost.
- Standardize technical validation across future flagship repositories.

## Assumptions

- PX4 SITL and ROS 2 can represent key integration behaviors for early validation.
- Not all physical effects will be captured; final validation still requires ground and controlled flight tests.
- Teams will maintain scenario and environment configuration version control.

## Risks

- Simulation-reality gap leading to false confidence
- Incomplete failure-injection coverage
- Drift between autopilot, ROS 2, and world-model versions
- Insufficient operator override modeling in simulation scenarios

## Alternatives Considered

1. Field-test-first development  
   - Rejected for safety, cost, and repeatability concerns.
2. Pure unit-test strategy without system simulation  
   - Rejected because cross-system timing and interface faults are missed.
3. Hybrid simulation-first with strict validation gates  
   - Selected baseline.

## Measurable Success Criteria

- Reproducible simulation bring-up in CI and local environments
- Versioned scenario catalog with documented expected outcomes
- Regression suite covering nominal, degraded, and failure conditions
- Traceable promotion criteria from SITL to HITL and controlled field tests

## Proposed Repository Structure

```text
hago-uav-simulation-lab/
  docs/
    architecture.md
    simulation-strategy.md
    scenario-catalog.md
    validation-gates.md
    limitations.md
  simulations/
    px4-sitl/
    ros2-gazebo/
    hitl/
  scenarios/
    nominal/
    degraded/
    failure-injection/
  tooling/
    orchestration/
    metrics/
  .github/workflows/
    ci-simulation.yml
```

## Validation Progression (Required)

1. Unit tests
2. Simulation component tests
3. Full-system SITL scenarios
4. Integration and regression tests
5. HITL (where available)
6. Controlled ground tests
7. Controlled flight tests
8. Operational validation

## Initial Scope (Phase 1 for this flagship)

- Baseline SITL environment definition
- Baseline ROS 2 + PX4 interface verification scenario
- Minimum scenario set:
  - nominal waypoint mission
  - telemetry degradation
  - GNSS disturbance simulation
  - perception confidence drop handling
- Validation gate definition for promotion to HITL planning

## Out of Scope (Phase 1)

- Claims of production readiness
- Broad hardware certification claims
- Autonomous deployment claims without reproducible evidence
