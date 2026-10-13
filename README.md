# Bare-metal Firmware Monorepo

A single repository for shared firmware modules
and mission-specific applications.

## Structure

- MCAL: Microcontroller abstraction layer
- DeviceDrivers: Common and payload drivers
- Services: Reusable firmware services
- MiddleWares: Middleware and protocols
- Subsystems: Functional firmware modules
- TaskLayer: Task and execution integration
- Interfaces: Shared interface definitions
- Missions: Mission1 and Mission2 applications
- tests: Unit tests and mocks
- scripts: Developer utilities
- docs: Architecture and development documentation

## Branch workflow

- feature/* -> develop
- develop -> main, by authorized release personnel only
- Feature PRs require one L1 and one L2 approval
