# UAT Test Cases

**Status:** Test cases are designed from the acceptance criteria of this case study. They have **not been formally executed**. SocioEcho was built as a team final-year project, but it implemented only part of the functionality documented here, so some test cases apply to features that do not exist yet.

During development, the project report describes functional testing by module: simulated logins from new IPs/devices and session timeouts, thread/comment/like/follow checks, and feeding toxic and clean inputs to the AI moderation. The test cases below are a structured UAT set written afterwards.

## UAT Approach
- **Participants:** students, an alumnus, a user who creates events and an administrator.
- **Entry criteria:** requirements approved; test data and user roles prepared.
- **Exit criteria:** all *Must* test cases pass; no open critical defects; stakeholder sign-off.
- **Defect handling:** logged with severity and linked to the requirement ID.

**Build column:** *Yes* = feature built, can be tested on the project. *Partial* = built in a different form. *No* = not built (future scope). *Verify* = built but the rule needs confirming. *Gap* = built, but it behaves differently from the requirement.

| TC | Req / Story | Scenario | Steps | Expected Result | Build |
|----|-------------|----------|-------|-----------------|-------|
| TC-01 | FR-04, US-01 | Follow a user | Open a mentor profile → Follow | User is followed | Partial |
| TC-02 | FR-04, US-01 | Search with no match | Search for a user or skill nobody matches | "No results" message with suggestion | Partial |
| TC-03 | FR-05, US-02 | Submit valid request | Choose category, enter details, submit | Saved as *Open*, confirmation shown | Verify (built as mentorship rooms) |
| TC-04 | FR-06, US-02 | Submit with missing category | Leave category empty, submit | Submission blocked, field highlighted | Verify |
| TC-05 | FR-07, US-06 | Mentor responds | Mentor opens matching request → responds | Status *Responded*, student notified | Partial |
| TC-06 | FR-07, US-06 | Respond to closed request | Mentor opens a *Resolved* request | View only, no respond option | No |
| TC-07 | FR-01–03, US-07 | Recommendations shown | Submit a Placement request | Relevant mentors and resources displayed | No |
| TC-08 | FR-02/03, US-07 | No mentor available | Submit a request with no matching mentor | Request stays *Open*, resources shown | No |
| TC-09 | FR-08, US-03 | Share resource | Alumnus or student uploads title, description, category | Resource visible to students with source and category | Yes |
| TC-10 | FR-08, NFR-04 | Unauthorized edit | Another user edits an alumnus's resource | Access denied | Verify |
| TC-11 | FR-09, NFR-04 | Session access control | Unauthorized user tries to join an AMA session | Access denied; authorized user joins | Verify |
| TC-12 | FR-10, US-05 | Publish event | Authorized organizer creates an event | Event appears on the board | Yes |
| TC-13 | FR-10, FR-14, NFR-04 | Student publishes event | Student tries to create an event | Option unavailable or denied | Gap (any user can create events) |
| TC-14 | FR-11, US-08 | Remove reported post | Admin removes a reported post | Post no longer visible; action logged | Yes |
| TC-15 | CR-01 | Multi-category request | Select Placement + Project, submit | Both categories saved | No |
| TC-16 | CR-01 | Regression: single category | Select one category, submit | Works as before | No |
| TC-17 | NFR-01 | Page load | Load key pages under normal load | 95% of loads ≤ 3 seconds | Yes (not measured) |
| TC-18 | NFR-02 | Data security | Inspect transport and storage of personal data | HTTPS used; passwords hashed | Yes |
| TC-19 | NFR-03 | Load test | Simulate 500 concurrent users | Degradation ≤ 10% | Yes (not measured) |
| TC-20 | NFR-05 | Usability | New student completes a key task unaided | Completed in ≤ 3 minutes | Yes (not measured) |
| TC-21 | FR-12, US-09 | Clean post is published | Submit a clean academic post | Post published and classified | Yes |
| TC-22 | FR-12, US-09 | Toxic post is blocked | Submit a post with toxic or profane text | Post blocked, user informed, outcome logged | Yes |
| TC-23 | FR-11, US-08 | Dismiss a report | Admin dismisses a report on a clean post | Post stays visible; report closed | Yes |
| TC-24 | FR-13, US-10 | Role-based signup and login | Sign up as Student, then Alumni; log in | Role-specific details requested; login succeeds | Yes |
| TC-25 | FR-13, NFR-04 | Unauthenticated access | Open a protected page without logging in | Access denied; redirected to login | Yes |
| TC-26 | FR-14, US-11 | Organizer approval | Admin approves an organizer; unapproved user tries to publish | Only approved organizer can publish | No |
| TC-27 | FR-15, US-12 | Track progress with tasks | Open a mentorship room → add a task → mark it complete | Task appears; status updates | Yes |

## Suggested Next Step
The hosted application is currently unavailable, so these test cases have not been run. Options to produce evidence for the cases marked *Yes*:
1. Run the project locally from its source code (frontend, backend and database connection) and record each result with a screenshot.
2. Redeploy the application, then run the cases.
3. If neither is possible, treat these as designed UAT cases. The project presentation screenshots in [Implementation-Evidence.md](Implementation-Evidence.md) show that the features existed.

Add a Result column once any case is executed.
