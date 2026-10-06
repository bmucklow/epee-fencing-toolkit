# ADR-001: Platform and distribution

**Status:** Accepted  
**Date:** 2026-10-06  
**Deciders:** Blaine + Engineering Lead (architecture) · Product · Design

## Context

30-day outcome requires an installable build on a real iPhone. Prior lean was App Store–ready Swift; phase-1 bar is TestFlight-class, not App Store submission.

## Decision

- **Stack:** Native Swift + SwiftUI  
- **Min iOS:** 17  
- **Distribution (30-day):** TestFlight (ad hoc acceptable fallback)  
- **Out of 30-day:** App Store submission, Android, cross-platform frameworks

## Consequences

- Enables SwiftData and `@Observable` for local-only persistence without legacy observation/Core Data boilerplate.  
- Builder needs Xcode, an Apple Developer account (Blaine creating), and Blaine’s test iPhone for the red-line check.  
- Design wireframes stay iOS-native (portrait-first, Dynamic Type, 44pt targets).
