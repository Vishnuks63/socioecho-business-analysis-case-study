# SocioEcho — Business Analysis Case Study

## Overview

SocioEcho is a college-focused student networking platform that connects students and alumni through verified profiles, AI-moderated academic discussions, task-based mentorship rooms, AMA sessions, an event board and a resource library.

This is a **portfolio case study** based on SocioEcho, my team's real final-year project. I documented it the way a Business Analyst would: problem definition → As-Is/To-Be analysis → requirements → process mapping → user stories and use cases → traceability → UAT test design → change-impact analysis → basic data analysis → Jira backlog.

> **Note:** The requirements documented here cover a fuller version of the platform than the one we implemented, so not every functionality described was built. The [RTM](Requirements-Traceability-Matrix.md) shows the build status of each requirement. Stakeholder needs other than the student and administrator perspectives are assumptions. Jira was used to practise Scrum backlog structuring rather than to run a live project. The dataset used in the data analysis is **simulated** (generated with an AI assistant) and was created only to demonstrate analysis techniques. Quantitative targets (response times, concurrency, etc.) are **illustrative assumptions**.

## Business Problem

Traditional social platforms lack academic context and expose students to distractions, misinformation and unmoderated content. Students find it hard to reach the right seniors or alumni for guidance, and useful resources are spread across many places. SocioEcho centralizes safe, role-verified academic interaction, resources, sessions and events.

## Implementation Status

| Status | Features |
|--------|----------|
| Implemented | Role-based signup/login (Student, Alumni) with an Administrator role, AI screening of posts (BART-large-MNLI) with manual administrator review of flagged/reported posts, follow, replies, real-time chat, task-based mentorship rooms, AMA sessions, Resource Library (shared by students and alumni) |
| Partial | Mentor responses (mentorship rooms and replies; no matching to expertise), Event Board (any user can create events; organizer-only restriction not built) |
| Future scope | personalised AI-based mentor and resource recommendations, analytics dashboard, job/internship integration, AI moderation of Resource Library uploads |

**Tech stack:** React, Redux, Tailwind CSS, Node.js, Express, MongoDB Atlas, JWT, bcrypt, BART-large-MNLI (Hugging Face).

## Document Index

| # | Deliverable | File |
|---|-------------|------|
| 1 | Business Requirements Document (BRD) | [Business-Requirements-Document.md](Business-Requirements-Document.md) |
| 2 | Stakeholder Analysis | [Stakeholder-Analysis.md](Stakeholder-Analysis.md) |
| 3 | As-Is / To-Be and Gap Analysis | [AsIs-ToBe-Gap-Analysis.md](AsIs-ToBe-Gap-Analysis.md) |
| 4 | Functional and Non-Functional Requirements | [Functional-and-Non-Functional-Requirements.md](Functional-and-Non-Functional-Requirements.md) |
| 5 | Process Map: Mentorship Request | [Mentorship-Request-Process.md](Mentorship-Request-Process.md) |
| 6 | Process Map: Content Moderation (implemented) | [Content-Moderation-Process.md](Content-Moderation-Process.md) |
| 7 | User Stories and Acceptance Criteria | [User-Stories-and-Acceptance-Criteria.md](User-Stories-and-Acceptance-Criteria.md) |
| 8 | Use Cases | [Use-Cases.md](Use-Cases.md) |
| 9 | Requirements Traceability Matrix (RTM) | [Requirements-Traceability-Matrix.md](Requirements-Traceability-Matrix.md) |
| 10 | UAT Test Cases | [UAT-Test-Cases.md](UAT-Test-Cases.md) |
| 11 | Change Impact Analysis | [Change-Impact-Analysis.md](Change-Impact-Analysis.md) |
| 12 | Data Analysis and Insights | [Data-Analysis-and-Insights.md](Data-Analysis-and-Insights.md) |
| 13 | Jira Implementation | [Jira-Implementation.md](Jira-Implementation.md) |
| 14 | Implementation Evidence (screenshots) | [Implementation-Evidence.md](Implementation-Evidence.md) |

## Traceability Chain

`Business Objective (BO) → Functional/Non-Functional Requirement (FR/NFR) → User Story (US) → Use Case (UC) → Test Case (TC)`

## Scope

**In scope:** mentorship requests, connections between students and alumni, resource sharing, mentorship (AMA) sessions, event publishing, AI-assisted content moderation with human review, role-based access.
**Out of scope:** physical/in-person mentorship coordination, general advertising, academic eligibility or access decisions (e.g., CGPA-based).

## Tools / Techniques

Requirements elicitation (based on own experience and assumptions), stakeholder analysis, As-Is/To-Be and gap analysis, process mapping (Mermaid flowcharts), BRD/FRD, user stories (Given-When-Then), use cases, MoSCoW prioritization, RTM, UAT test design, change-impact analysis, descriptive data analysis on simulated data (Power BI), and Jira (Scrum) used to practise backlog structuring (epics, stories, subtasks).

**Author:** Vishnu K S
