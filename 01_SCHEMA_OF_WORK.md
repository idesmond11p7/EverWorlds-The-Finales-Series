# Schema of Work

[ID: SCH-01]
[STATUS: ACTIVE / MASTER ROUTER]
[LAST-UPDATED: 2026-10-06 | TIME: UNKNOWN]
[UPSTREAM: CG-00]
[DOWNSTREAM: ALL]

## Function
Opaque routing layer. Filenames are aliases. IDs are authority.

## Core modules
CG-00 CONTROL
SCH-01 SCHEMA
MAP-02 DOCUMENT GRAPH
SRC-03 SOURCE LEDGER
QTE-04 QUOTE LEDGER
DEC-05 DECISION LEDGER
MMG-06 MENTAL MODEL GRADES
CAN-07 CANON CLAIM MATRIX
IDE-08 IDEA REGISTRY
CHR-09 CHAPTER REGISTRY
PRO-10 PROSE ARCHITECTURE
MET-11 PROSE MEASUREMENT
WRK-12 WORK LOG
REC-13 RECOVERY / QUARANTINE
AUD-14 AUDIT / RELEASE
HND-15 SESSION HANDOFF
INP-16 INPUT REQUIREMENTS
ARC-17 ARCHIVE INDEX

## Atomicity rule
A module is a reusable information surface, not a topic bucket. One concept may have records across source, quote, model, canon, chapter, and prose modules.

## Mental-model axis
Every important record receives G1, G2, or G3:
- G1 = one-dimensional / flat / collapsed.
- G2 = partially structured / unique structure exists but information remains collapsed.
- G3 = fully operational mental model: components, relations, boundaries, interactions, exceptions, consequences and usage are understood.

GRADE IS NOT CANONICITY.

## Evidence axis
SOURCE / AUTHOR / VERIFIED / DERIVED / PROVISIONAL / RECONSTRUCTION / RETRACTED / UNKNOWN.

## Operational axis
UNUSABLE / REFERENCE-ONLY / OPERATIONAL / VERIFIED-IN-USE.

## Creation rule
No new module without ID, purpose, upstream, downstream, schema, evidence rules, grade rules, and retirement path.
