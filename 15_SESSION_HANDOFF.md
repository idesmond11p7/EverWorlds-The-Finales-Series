# Session Handoff

[ID: HND-15]
[STATUS: ACTIVE / SESSION BRIDGE]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: WRK-12, AUD-14]
[DOWNSTREAM: CG-00]

## Purpose
A later session must recover the exact state without trusting conversational memory.

## Required fields
SESSION-ID
DATE
START-TIME
END-TIME
EXACT-LAST-ACTION
TARGET-ID
FILES-TOUCHED
SOURCES-READ
QUOTES-ADDED
DECISIONS
GRADE-CHANGES
INVALIDATED-CLAIMS
STALE-DEPENDENTS
VERIFICATION
OPEN-QUESTIONS
BLOCKERS
NEXT-SAFE-ACTION
STOP-CONDITIONS

## Rule
If the next safe action depends on a missing artifact, state the missing artifact explicitly.
