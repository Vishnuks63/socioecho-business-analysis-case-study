# Change Impact Analysis

## Change Request

| Field | Detail |
|-------|--------|
| ID | CR-01 |
| Title | Allow multiple guidance categories per request |
| Raised by | BA (case-study scenario) |
| Priority | Should |
| Effort (assumed) | Medium |
| Status | Proposed, pending approval |

### Current State
A student selects one guidance category when creating a mentorship request.

### Requested Change
A student can select multiple categories, for example Placement + Project + Career.

### Rationale
Real requests often span areas (a placement question that needs project advice). A single category forces students to submit duplicate requests or pick an inaccurate one.

## Impact Assessment

| Area | Impact |
|------|--------|
| Requirement | FR-06 must support multiple categories |
| User Story | US-02 affected |
| Use Case | UC-01 gains alternate flow A1 |
| Acceptance Criteria | Category selection and validation criteria must be updated |
| Process | Categorization changes from single-select to multi-select |
| Matching | Mentor/resource matching must consider all selected categories (FR-01 to FR-03) |
| UI | Category field becomes multi-select |
| Data | Request records must store multiple categories |
| Reporting | Category analysis must count a request under each category (affects data analysis) |
| Testing | TC-04, TC-15, TC-16 added or updated |
| Traceability | RTM rows for FR-05, FR-06 updated |
| Jira | US-02 and its subtasks updated |
| Risk | A selected category could be ignored during matching |

## Open Questions
- Is there a maximum number of categories per request?
- How are mentors ranked when they match only some of the categories?

## Recommendation
Approve with a limit of three categories. Update FR-06, US-02, UC-01, the RTM and the test cases, and re-test matching before release.

## BA Approach
The analysis identifies what changed, which requirements and solution components are affected, and what documentation and testing must be updated.

---

# Change Request CR-02

| Field | Detail |
|-------|--------|
| ID | CR-02 |
| Title | Restrict event creation to authorized organizers |
| Raised by | BA (gap found between requirement and build) |
| Priority | Should |
| Effort (assumed) | Small to Medium |
| Status | Proposed |

### Current State
Any logged-in user can create an event on the Event Board.

### Requested Change
Only users approved by an administrator as organizers can create or edit events. Other users can view events only.

### Rationale
Open event creation can lead to irrelevant or spam listings and reduces trust in the Event Board. Requirement BR-04 (organizer-only publishing) was not met by the build.

## Impact Assessment

| Area | Impact |
|------|--------|
| Requirement | FR-10 clarified; FR-14 (organizer authorization) implemented |
| User Story | US-05 AC3 now met; US-11 added to the build |
| Use Case | UC-04 alternate flow A1 becomes real |
| Roles / Access | New organizer permission (role or flag) enforced by RBAC (NFR-04) |
| Admin function | Administrator needs a way to approve and revoke organizers |
| UI | "Create event" hidden for non-organizers |
| Data | User record gains an organizer status |
| Existing data | Decide whether existing events by non-organizers stay visible |
| Testing | TC-13 and TC-26 become pass/fail checks |
| Traceability | RTM rows for FR-10 and FR-14 updated to Implemented |
| Risk | Fewer events posted if approval is slow |

## Open Questions
- Who approves organizers (admin only, or faculty coordinators)?
- Should approved organizers be able to edit or delete each other's events?

## Recommendation
Approve. Add an organizer approval step to the admin tools and enforce the permission in the event creation endpoint, not only in the UI. Re-test access control before release.
