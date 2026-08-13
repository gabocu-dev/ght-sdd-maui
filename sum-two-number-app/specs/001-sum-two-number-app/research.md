<!-- SDD Artifact | Version: 1.0 | Phase: Plan | Updated: 2026-08-13 -->
<!-- Project: sum-two-number-app | Feature: 001-sum-two-number-app -->

# Research Notes: Sum Two Number App

## Summary
A local-only mobile calculator app is best served by a lightweight cross-platform framework. .NET MAUI with Blazor Hybrid provides a familiar C# development model, easy validation, and fast app setup for a simple arithmetic use case.

## Findings
- The app needs only a small UI surface and a simple calculation service.
- No persisted data or external services are required.
- The chosen stack supports fast iteration and reasonable testing for a simple app.
- A minimal CI/CD pipeline can validate builds without adding operational overhead.

## Decisions
- Use .NET MAUI with Blazor Hybrid for the front end.
- Keep business logic in a dedicated local service so it remains reusable.
- Use in-memory values rather than database or storage.
- Keep deployment to local device/emulator testing and GitHub build validation.
