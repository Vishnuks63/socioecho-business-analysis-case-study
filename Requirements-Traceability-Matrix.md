# Requirements Traceability Matrix (RTM)

Traceability: **Objective → Requirement → User Story → Use Case → Test Case**, plus **build status** in the SocioEcho final-year project.

| Req ID | Requirement (short) | Objective | User Story | Use Case | Test Cases | Build Status |
|--------|---------------------|-----------|------------|----------|------------|--------------|
| FR-01 | Identify topics/categories | BO-02 | US-07 | UC-01 | TC-07 | Partial |
| FR-02 | Recommend seniors/alumni | BO-02 | US-01, US-07 | UC-01 | TC-07, TC-08 | Not implemented |
| FR-03 | Recommend resources | BO-02 | US-07 | UC-01 | TC-07, TC-08 | Not implemented |
| FR-04 | Follow/connect with users | BO-01 | US-01 | none | TC-01, TC-02 | Implemented |
| FR-05 | Create and submit request | BO-01 | US-02 | UC-01 | TC-03, TC-15 | Implemented (mentorship rooms) |
| FR-06 | Specify category and details | BO-01 | US-02 | UC-01 | TC-04, TC-15, TC-16 | Partial |
| FR-07 | Mentors view and respond | BO-03 | US-06 | UC-02 | TC-05, TC-06 | Partial |
| FR-08 | Share resources | BO-04 | US-03 | UC-03 | TC-09, TC-10 | Implemented |
| FR-09 | Create/join sessions | BO-01, BO-04 | US-04 | none | TC-11 | Implemented |
| FR-10 | Publish events | BO-05 | US-05 | UC-04 | TC-12, TC-13 | Partial (any user can create) |
| FR-11 | Review reported content, remove | BO-06 | US-08 | UC-05 | TC-14, TC-23 | Implemented (posts) |
| FR-12 | Screen posts before publication | BO-06 | US-09 | UC-05 | TC-21, TC-22 | Implemented |
| FR-13 | Role-based signup and login | BO-06 | US-10 | none | TC-24, TC-25 | Implemented |
| FR-14 | Authorize event organizers | BO-05, BO-06 | US-11 | UC-04 | TC-13, TC-26 | Not implemented |
| FR-15 | Track mentorship progress with tasks | BO-04 | US-12 | none | TC-27 | Implemented |
| NFR-01 | Page load time | BO-01 | none | none | TC-17 | Not measured |
| NFR-02 | Data security | BO-06 | US-10 | none | TC-18 | Implemented |
| NFR-03 | Concurrent usage | none | none | none | TC-19 | Not measured |
| NFR-04 | Role-based access | BO-06 | US-03, US-05, US-08, US-10 | none | TC-10, TC-11, TC-13, TC-25 | Implemented |
| NFR-05 | Usability | none | none | none | TC-20 | Not measured |
| NFR-06 | Availability | none | none | none | Monitoring after release | Not measured |

## Build Status Summary

| Status | Requirements |
|--------|--------------|
| Implemented | FR-04, FR-05, FR-08, FR-09, FR-11 (posts), FR-12, FR-13, FR-15, NFR-02, NFR-04 |
| Partial | FR-01, FR-06, FR-07, FR-10 |
| Not implemented (future scope) | FR-02, FR-03 |
| Recommended improvement | FR-14 (organizer-only event publishing, see CR-02) |
| Not measured | NFR-01, NFR-03, NFR-05, NFR-06 |

## Features Built Outside This Case Study's Scope
The project also implemented an academic feed, likes, threaded replies and real-time chat by department or topic. These are not traced here because the case study focuses on mentorship, resources, events and moderation.

## Gaps Between Requirement and Build
| Gap | Requirement | Build | Action |
|-----|-------------|-------|--------|
| G-01 | Only authorized organizers publish events (BR-04, FR-14) | Any logged-in user can create events | Change request CR-02 |
| G-02 | Students, alumni, faculty and seniors share resources (FR-08) | Student and Alumni logins share; no faculty role | Seniors are students, so covered. Faculty role is future scope |
| G-03 | Personalised mentor and resource recommendations (FR-02, FR-03) | A non-personalised panel of available communities and popular users | Future scope |

## Coverage Check
- Every requirement maps to at least one user story (functional) and one test case.
- Every business objective (BO-01 to BO-06) is covered by at least one requirement.

## Purpose
The RTM links each business objective to requirements, stories, use cases and tests. It supports requirement validation, UAT, change analysis (see [CR-01](Change-Impact-Analysis.md)), and shows which scope was built and which remains future work.
