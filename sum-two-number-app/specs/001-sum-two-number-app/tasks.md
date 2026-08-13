<!-- SDD Artifact | Version: 1.0 | Phase: Tasks | Updated: 2026-08-13 -->
<!-- Project: sum-two-number-app | Feature: 001-sum-two-number-app -->

# Task Breakdown: Sum Two Number App

## Conventions
- [P] = Can run in parallel
- [Story: US-001] = User story this task belongs to
- [Dep: T-NNN] = Depends on task T-NNN
- File paths are relative to project root
- Tests included ONLY if required by constitution or spec

## Phase 0: Foundational Setup
- [ ] T-001: Initialize the .NET MAUI Blazor Hybrid project structure [P]
  - Files: src/, tests/, .gitignore, global.json, Directory.Build.props
  - Acceptance: App shell builds successfully with no compile errors
- [ ] T-002: Configure development and CI environment [P]
  - Files: .github/workflows/build.yml, appsettings.json, README.md
  - Acceptance: Build runs in a clean environment and local app can launch
### Checkpoint: Foundational
- [ ] App shell compiles, project structure is stable, and CI can run a clean build

## Phase 1: User Story US-001 — Add two numbers quickly
Priority: Must Have
- [ ] T-010: Create the local calculation service [Dep: T-001]
  - Files: src/Services/CalculatorService.cs
  - Acceptance: Service accepts two numeric values and returns their sum
- [ ] T-011: Build the app UI for two input fields and the calculate action [Dep: T-001] [P]
  - Files: src/Components/*, src/Pages/*
  - Acceptance: Screen displays inputs and action controls for entering values
- [ ] T-012: Wire UI to the calculation service and render results [Dep: T-010, T-011]
  - Files: src/Pages/CalculatorPage.razor, src/Services/CalculatorService.cs
  - Acceptance: User enters two numbers and sees the correct total after triggering the action
- [ ] T-013: Add small validation and reset behavior [Dep: T-012] [P]
  - Files: src/Components/*, src/Pages/*
  - Acceptance: Invalid or empty input is handled gracefully and users can clear the form
- [ ] T-014: Add focused tests for calculation and UI flow [Dep: T-012]
  - Files: tests/Unit/CalculatorServiceTests.cs, tests/Integration/CalculatorFlowTests.cs
  - Acceptance: Valid input returns correct sum and the app flow is stable
### Checkpoint: US-001
- [ ] User can enter two numbers and obtain the correct sum
- [ ] Core acceptance criteria pass on the selected mobile runtime

## Phase 2: Integration & Polish
- [ ] T-090: Run a final build and device validation pass
- [ ] T-091: Review the app against success criteria and scope boundaries
- [ ] T-092: Final documentation and handoff review

## Dependency Summary
T-001 ──┬── T-010
         ├── T-011 ──┬── T-012 ── T-013
         │            └── T-014
         └── T-002

## Backlog Mapping
| Task | GitHub Label | ADO Type | Priority |
|------|-------------|----------|----------|
| T-001..002 | phase:foundation | Task | P0 |
| T-010..014 | story:US-001 | PBI | Must Have |
| T-090..092 | phase:integration | Task | P1 |