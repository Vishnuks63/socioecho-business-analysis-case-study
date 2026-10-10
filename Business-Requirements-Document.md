# Business Requirements Document — SocioEcho

| Field | Detail |
|-------|--------|
| Version | 1.1 |
| Author | Vishnu K S |
| Status | Portfolio case study (based on a team final-year project; covers a fuller scope than was implemented) |
| Last updated | October 2026 |

## 1. Purpose
This document defines the business need, objectives, scope and constraints for SocioEcho. Detailed solution requirements are in the [Functional and Non-Functional Requirements](Functional-and-Non-Functional-Requirements.md).

## 2. Project Overview
SocioEcho is a college-focused social networking and mentorship platform connecting students, seniors, alumni, faculty/mentors and event organizers. It supports academic guidance, career development, mentorship, networking, resource sharing and events.

## 3. Problem Statement
Students may not know whom to approach for academic, career, placement and project guidance. Seniors and alumni lack visibility into which students need help and what type of help is needed. Alumni have limited time to respond individually, and useful resources are spread across websites, portals and social groups. See the [As-Is / To-Be analysis](AsIs-ToBe-Gap-Analysis.md).

## 4. Business Objectives and Success Measures

| ID | Objective | Success Measure | Target (illustrative) |
|----|-----------|-----------------|-----------------------|
| BO-01 | Enable students to communicate academic, career, placement and project guidance needs | % of requests submitted with a category and details | ≥ 95% |
| BO-02 | Provide centralized access to relevant resources and mentorship | % of requests that receive at least one relevant resource/mentor recommendation | ≥ 90% |
| BO-03 | Enable seniors/alumni to identify students needing assistance | Average mentor response time | ≤ 24 hours |
| BO-04 | Enable alumni to support multiple students efficiently | Request resolution rate; resources shared per alumnus | ≥ 80% resolved |
| BO-05 | Enable authorized organizers to publish relevant events and opportunities | Events published per month; share of students viewing at least one event | To be baselined |
| BO-06 | Maintain a safe, trusted, academic-focused environment | % of posts screened before publication; reported posts reviewed within a set time | 100% screened; reviewed ≤ 48 hours |

*Targets are assumptions for illustration. The simulated dataset shows a baseline of 18.97 hours average response time and 80% resolution (see [Data Analysis](Data-Analysis-and-Insights.md)).*

## 5. Scope
**In scope:** mentorship requests; connections between students, seniors and alumni; resource sharing; mentorship sessions; event/opportunity publishing; AI-assisted content moderation with human review; role-based registration and secure login; organizer authorization.
**Out of scope:** physical/in-person mentorship coordination; general advertising; academic eligibility/access decisions.

## 6. Stakeholders
Students, senior students, alumni, faculty/college mentors, authorized event organizers, platform administrator. Details in [Stakeholder-Analysis.md](Stakeholder-Analysis.md).

## 7. High-Level Solution
Structured mentorship requests, profile-based connections, recommendations, resource sharing, mentorship sessions and an event board in one centralized platform.

## 8. Assumptions
- A-01: Users are verified members of the college community (students, alumni, faculty).
- A-02: Alumni and seniors are willing to volunteer time for mentoring.
- A-03: Users have internet access on mobile or desktop.
- A-04: Guidance categories are limited to Academic, Placement, Project and Career for the first release.

## 9. Constraints
- C-01: Personal data must be handled securely (see NFR-02).
- C-02: First release is limited to one college.
- C-03: Mentors participate voluntarily; response times cannot be contractually enforced.

## 10. Dependencies
- D-01: Access to a verified list of students/alumni for onboarding.
- D-02: College approval process for authorizing event organizers.

## 11. Risks

| ID | Risk | Impact | Likelihood | Mitigation |
|----|------|--------|-----------|------------|
| R-01 | Low mentor participation | High | Medium | Resource sharing reduces repeat questions; recognize active mentors |
| R-02 | Poor mentor/resource matching | Medium | Medium | Clear matching rules; fallback to resources; review matching accuracy |
| R-03 | Misuse or inappropriate content | Medium | Medium | AI screening before publication (FR-12) plus human review of reported posts (FR-11) |
| R-04 | Personal data exposure | High | Low | NFR-02 and NFR-04; role-based access |
| R-05 | Unauthorized event posting | Low | Medium | Organizer authorization (FR-10, FR-11) |

## 12. Open Questions
- OQ-01: What is the business rule for requests with no suitable mentor? (see [process map](Mentorship-Request-Process.md))
- OQ-02: Which communication mode do mentorship sessions use (text chat, video, both)?
- OQ-03: How should mentors be ranked when several match a request?
- OQ-04: Should event creation be restricted to authorized organizers? (In the build, any user can create events. Content moderation is AI screening plus manual administrator review.)

## 13. Glossary
**Mentor:** senior student, alumnus or faculty member who responds to requests. **Request:** a student's guidance need with a category and details. **Resource:** a document or link shared for students. **Session:** a mentor-led discussion. **RTM:** Requirements Traceability Matrix.

## 14. Implementation Status
SocioEcho was built as a team final-year project. This BRD covers a fuller scope than was implemented. Implemented: role-based registration and login, posts with AI screening and human moderation, follow, replies, real-time chat, task-based mentorship rooms, AMA sessions, Event Board (open to all users; organizer-only restriction not built), Resource Library (Student and Alumni logins). Not implemented (future scope): personalised recommendations, analytics dashboard, job/internship integration, AI moderation of Resource Library uploads. See the [RTM](Requirements-Traceability-Matrix.md) for requirement-level status.
