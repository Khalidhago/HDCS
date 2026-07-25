# Safety and Cybersecurity Boundaries

## Purpose

Define non-negotiable safety and cybersecurity constraints for UAV/UAS development, simulation, and testing.

## Safety Boundaries

1. **Autopilot authority boundary**
   - Low-level stabilization and failsafes remain in certified/validated autopilot domain.
2. **Autonomy constraint boundary**
   - High-level autonomy outputs must pass safety gates before actuation.
3. **Operational envelope boundary**
   - Test and mission profiles must define speed, altitude, geofence, weather, and payload constraints.
4. **Verification boundary**
   - Progression path: unit tests → simulation → SITL → integration → HITL/bench → controlled field tests.
5. **Evidence boundary**
   - No claims of flight-ready or production-ready status without documented V&V evidence.

## Cybersecurity Boundaries

1. **Identity and access**
   - Principle of least privilege for repos, CI, and deployment systems.
2. **Secret handling**
   - No hardcoded credentials; use secret stores and rotation policy.
3. **Dependency trust**
   - Use dependency scanning and pin known-good versions where feasible.
4. **Comms hardening**
   - Protect telemetry/control links and document threat assumptions.
5. **Data protection**
   - Define data classes, retention, and access controls for mission and sensor data.

## Assumptions

- Threat actors may attempt RF interception, spoofing, and command injection.
- Field connectivity is unreliable; safety cannot depend on cloud availability.
- Human operators remain accountable for final mission approval.

## Key Risks

- Unsafe autonomy behavior due to stale or low-confidence perception
- Misconfigured command permissions between companion and autopilot
- Secret leakage via code, CI logs, or artifacts
- Inadequate regression testing after interface changes

## Minimum Acceptance Criteria

- Documented safety case per major autonomy feature
- Security scanning integrated into repository workflow
- Explicit operator override and mission abort mechanisms
- Reproducible validation artifacts for each maturity-state claim
