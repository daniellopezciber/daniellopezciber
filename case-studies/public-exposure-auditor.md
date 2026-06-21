# Public Exposure Auditor

> Public case study. The full source code is private to protect project logic, dork sets, validation rules and responsible disclosure details.

## Summary

Public Exposure Auditor is a Python-based OSINT prototype designed to identify publicly exposed sensitive information on the open web and support responsible notification workflows.

The project was built to detect risky public exposures such as misconfigured cloud storage, exposed configuration files, leaked credentials, SQL dumps and sensitive documents indexed by search engines.

## Problem

Many organizations expose sensitive files accidentally through:

- Misconfigured cloud buckets.
- Publicly indexed `.env` files.
- Backup files.
- SQL dumps.
- Forgotten staging environments.
- Documents exposed through search engines.

Manual discovery is slow and inconsistent. The goal was to build a repeatable pipeline that could discover, triage and organize findings for responsible reporting.

## Solution

The system uses a multi-stage pipeline:

1. Generate targeted search queries for public exposure patterns.
2. Query search sources through an automated acquisition layer.
3. Clean and normalize returned URLs.
4. Store raw matches in JSONL for traceability.
5. Deduplicate results.
6. Triage findings into a verification list.
7. Prepare responsible disclosure notifications.

## Architecture

```mermaid
flowchart LR
    A["Dork Query Sets"] --> B["Acquisition Engine"]
    B --> C["URL Normalization"]
    C --> D["JSONL Evidence Buffer"]
    D --> E["Triage and Deduplication"]
    E --> F["Verification List"]
    F --> G["Responsible Notification"]
```

## Technical Highlights

- Python-based acquisition engine.
- Search-query automation through public search sources.
- Regex-based URL cleanup and filtering.
- JSON Lines persistence for raw evidence.
- Deduplication and verification pipeline.
- Randomized waiting strategy to reduce request pressure.
- Responsible reporting workflow for affected organizations.

## Stack

- Python
- Regex
- JSONL
- OSINT methodology
- Search dorking
- Responsible disclosure process

## Results

- Built and executed a functional public exposure audit workflow.
- Identified real exposed information affecting external organizations.
- Sent responsible notification emails to affected institutions.
- Received acknowledgements from some contacted organizations.

Specific targets, company names, query sets and findings are intentionally omitted.

## Security and Ethics

This project was designed for defensive research and responsible disclosure. The public case study excludes:

- Exact dork sets.
- Target names.
- Finding URLs.
- Sensitive screenshots.
- Exploit logic.
- Notification templates with real recipients.

## What I Learned

- How to structure OSINT findings into a repeatable workflow.
- How to separate acquisition, persistence and triage.
- How to reduce false positives through filtering.
- Why responsible disclosure requires careful wording and restraint.
- How to document sensitive cybersecurity work without exposing harmful details.

## Future Improvements

- Add LLM-assisted report drafting with strict redaction.
- Add domain and cloud-provider classification.
- Add confidence scoring for findings.
- Add a dashboard for triage status.
- Add rate-limit aware scheduling.
- Add encrypted local evidence storage.

## Portfolio Value

This project demonstrates practical experience in:

- Python automation.
- Cybersecurity research.
- OSINT.
- Cloud exposure awareness.
- Responsible disclosure.
- Risk triage workflows.
