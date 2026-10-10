# Functional and Non-Functional Requirements (FRD)

Priority uses MoSCoW (Must, Should, Could). **Build status** shows what the SocioEcho final-year project actually implemented: *Implemented*, *Partial*, or *Not implemented* (future scope or recommended improvement).

## Functional Requirements

| ID | Requirement | Priority | Objective | User Story | Build Status |
|----|-------------|----------|-----------|------------|--------------|
| FR-01 | Identify relevant topics/categories from a request or post | Should | BO-02 | US-07 | Partial: posts are classified into academic communities (zero-shot); not applied to mentorship requests |
| FR-02 | Recommend relevant seniors/alumni based on skills, experience or expertise | Should | BO-02 | US-01, US-07 | Not implemented (future scope) |
| FR-03 | Recommend relevant resources based on topics/categories | Should | BO-02 | US-07 | Not implemented (future scope). A non-personalised panel of available communities and popular users exists |
| FR-04 | Allow students to follow/connect with seniors/alumni | Must | BO-01 | US-01 | Implemented: follow users; find users by unique ID (no search by skill) |
| FR-05 | Allow students to create and submit mentorship requests | Must | BO-01 | US-02 | Implemented: task-based mentorship rooms where a student books mentorship help (request fields to confirm) |
| FR-06 | Allow students to specify guidance categories and request details | Must | BO-01 | US-02 | Partial: details captured in mentorship rooms; guidance category selection to confirm; posts are auto-classified |
| FR-07 | Allow relevant seniors/alumni to view and respond to requests | Must | BO-03 | US-06 | Partial: mentors respond in mentorship rooms and threaded replies (accept/decline flow to confirm); no matching to mentor expertise |
| FR-08 | Allow students and alumni (faculty assumed) to upload/share academic and career resources | Must | BO-04 | US-03 | Implemented: Resource Library; Student and Alumni logins can share; no faculty role |
| FR-09 | Allow authorized participants to create/join mentorship sessions | Should | BO-01, BO-04 | US-04 | Implemented: AMA sessions and real-time chat |
| FR-10 | Allow authorized organizers to publish events and opportunities | Should | BO-05 | US-05 | Partial: Event Board built, but any logged-in user can create events (organizer-only not built) |
| FR-11 | Allow administrators to manually review flagged/reported content and remove inappropriate content | Must | BO-06 | US-08 | Implemented for posts: any user can report, admin reviews manually; Resource Library moderation is future scope |
| FR-12 **(new)** | Screen posts before publication for toxicity, profanity and insults, and block those flagged | Must | BO-06 | US-09 | Implemented: BART-large-MNLI classifier |
| FR-13 **(new)** | Role-based registration (Student/Alumni) and secure login | Must | BO-06 | US-10 | Implemented: JWT, bcrypt, suspicious-login detection |
| FR-14 **(new)** | Allow administrators to authorize event organizers | Should | BO-05, BO-06 | US-11 | Not implemented (recommended improvement, see CR-02) |
| FR-15 **(new)** | Track mentorship progress through tasks | Should | BO-04 | US-12 | Implemented: task-based mentorship rooms |

## Non-Functional Requirements

*Targets are illustrative assumptions to be validated with stakeholders.*

| ID | Category | Requirement | Measure | Build Status |
|----|----------|-------------|---------|--------------|
| NFR-01 | Performance | Key pages load quickly under expected usage | 95% of page loads ≤ 3 seconds | Not measured |
| NFR-02 | Security | Personal information stored and transmitted securely | HTTPS/TLS in transit; passwords hashed; data encrypted at rest | Implemented: bcrypt hashing, JWT sessions, encrypted MongoDB Atlas connections |
| NFR-03 | Scalability | Supports expected concurrent usage without degradation | 500 concurrent users, ≤ 10% slower response | Not measured |
| NFR-04 | Access control | Only authorized users access restricted functions | Role-based access; unauthorized attempts denied and logged | Implemented: RBAC |
| NFR-05 | Usability | Interface is understandable for the target audience | First-time student submits a request in ≤ 3 minutes unaided | Not measured |
| NFR-06 | Availability | Platform available when students need it | 99% uptime during academic hours | Not measured (cloud database with automated backups) |

## Business Rules
- BR-01: A request must have at least one category and a description.
- BR-02: Only users with mentor roles can respond to requests.
- BR-03: Only the owner or an administrator can edit or delete a resource.
- BR-04: Only authorized organizers can publish events. *(Not enforced in the build: any user can create events. See CR-02.)*
- BR-05: Every post is screened before it becomes visible to others.
- BR-06: Reported or flagged posts are reviewed manually by an administrator.
- BR-07: Moderation outcomes are recorded in moderation logs.

## BA Principle Applied
Functional requirements describe **what** the solution does. Non-functional requirements describe **how well, or under what constraints**, it operates.
