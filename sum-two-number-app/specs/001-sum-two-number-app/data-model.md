<!-- SDD Artifact | Version: 1.0 | Phase: Plan | Updated: 2026-08-13 -->
<!-- Project: sum-two-number-app | Feature: 001-sum-two-number-app -->

# Data Model: Sum Two Number App

## Domain Model
The application does not require persistent storage. It operates with lightweight in-memory state that is created when a user starts a calculation session.

### Entity: Number Input
Purpose: Holds the two numeric values the user enters.
Attributes:
- First value
- Second value
Relationships:
- Used as input to the calculation process

### Entity: Calculation Result
Purpose: Stores the computed total visible to the user.
Attributes:
- Total value
Relationships:
- Derived from the two number inputs

### Entity: App Session State
Purpose: Represents the currently active calculator state.
Attributes:
- Current values
- Current result
- Reset status
Relationships:
- Keeps the form and result in sync during a single interaction cycle

## Model Constraints
- No database persistence is required.
- Values are ephemeral during the active app usage.
- Inputs are expected to be numeric for the successful path.
