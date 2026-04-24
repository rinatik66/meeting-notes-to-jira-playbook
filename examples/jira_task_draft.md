# Jira Task Draft

## Summary
Stabilize macOS meeting audio capture workflow for transcript generation

## Background
Current meeting-note workflow depends on reliable audio capture. Existing setups degrade when multiple sources are mixed or sample rates drift.

## Problem
Transcript quality drops over time in multi-source sessions, which makes downstream notes less reliable.

## Proposed scope
- test a simplified Audio Hijack chain
- document supported capture scenarios
- define fallback setup for VDI meetings

## Open questions
- do we need one standard setup for all meeting types?
- should VDI capture have a separate operating guide?

## Expected result
A stable, documented capture workflow that produces transcript-ready audio for the main meeting scenarios.

## Links
- source note: [[2026.04.24 Weekly sync]]
- related doc: [[Audio capture on macOS]]
