# Flagship Specification: hago-px4-autonomy-platform

## Status

`concept`

## One-Sentence Technical Description

PX4-centered autonomy platform defining safe mission-level control, MAVLink interfaces, companion-computer integration, and simulation-to-field validation pathways for UAV/UAS operations.

## Mission Statement

Deliver a reusable and safety-constrained autonomy foundation that integrates PX4 autopilot capabilities with mission logic and perception-driven decision support while preserving explicit human oversight boundaries.

## Engineering Reason

- Standardize how autonomy features interact with PX4 flight modes and failsafes.
- Reduce integration ambiguity between flight-control, ROS 2, and mission-application teams.
- Create a reproducible path from simulated autonomy experiments to controlled real-world validation.

## Assumptions

- PX4 remains authoritative for low-level stabilization and critical failsafe actions.
- Mission/autonomy layers issue bounded commands through validated interfaces only.
- Telemetry and command links can degrade and must be modeled as failure conditions.

## Risks

- Command-authority confusion between autonomy layer and operator controls
- Unsafe transitions across flight modes during degraded conditions
- Autonomy over-reliance on uncertain perception or stale state
- Version drift in PX4/MAVLink dependencies causing interface breakage

## Alternatives Considered

1. Direct custom flight-control loops on companion computer  
   - Rejected for safety and maintainability risks.
2. Minimal autonomy with only manual mission operation  
   - Viable for early operations but insufficient for scalable mission capability.
3. Bounded autonomy on top of PX4 with strict safety gates  
   - Selected baseline.

## Measurable Success Criteria

- Documented command authority matrix for manual, assisted, and autonomous modes
- Repeatable SITL scenarios validating flight-mode transitions and failsafe behavior
- Clear interface contracts for MAVLink command/telemetry pathways
- Traceable promotion criteria from simulation evidence to controlled test progression

## Proposed Repository Structure

```text
hago-px4-autonomy-platform/
  docs/
    mission-statement.md
    architecture.md
    command-authority-matrix.md
    interface-contracts.md
    safety-case.md
    validation-plan.md
    limitations.md
  configs/
    px4/
    mission-profiles/
  integrations/
    mavlink/
    ros2-bridge/
  simulations/
    sitl-scenarios/
    failure-injection/
  tests/
    interface/
    mission-logic/
```

## Architecture Boundaries

- **PX4 domain:** stabilization, control loops, arming logic, core failsafes
- **Autonomy domain:** mission sequencing, decision policies, route/task adaptation
- **Interface domain:** MAVLink messages, command acknowledgment, state reporting
- **Human-in-loop domain:** override and abort authority preserved for defined mission classes

## Validation Gates

1. Interface/unit tests for command and telemetry handling
2. SITL regression for nominal and degraded mission scenarios
3. Mode-transition and failsafe scenario verification
4. Integration checks with ROS 2 and mission services
5. Controlled ground-testing checklist completion
6. Controlled flight-test readiness review with explicit risk acceptance

## Maturity Policy for this Flagship

- `concept`: architecture and safety boundaries documented
- `prototype`: SITL scenarios and baseline integration evidence available
- `ground-tested`: controlled bench/ground validation evidence available
- `flight-tested`: controlled flight evidence available
- `production-candidate`: repeatable validation, documentation completeness, and risk controls established

No maturity status may be advanced without objective evidence artifacts.
