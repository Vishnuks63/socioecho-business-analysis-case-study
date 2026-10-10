# Use Cases

## UC-01 — Submit Mentorship Request
*Build note: implemented in SocioEcho as task-based mentorship rooms. The recommendation step (step 6) is not built.*

| Field | Detail |
|-------|--------|
| Actor | Student |
| Related | FR-01 to FR-03, FR-05, FR-06 · US-02, US-07 |
| Precondition | Student is logged in |
| Trigger | Student needs guidance |
| Postcondition | Request is saved with status *Open*; mentors and resources are recommended |

**Main flow**
1. Student selects *Create Request*.
2. Student selects a guidance category and enters details.
3. Student submits.
4. System validates the input (BR-01).
5. System saves the request as *Open*.
6. System identifies topics and recommends mentors and resources.
7. System notifies relevant mentors and shows a confirmation.

**Alternate flow**
- A1: Multiple categories selected (if CR-01 is approved): the system saves all categories and matches on each.

**Exception flows**
- E1: Category or details missing → system blocks submission and highlights the fields.
- E2: No suitable mentor → request stays *Open* and relevant resources are shown.

## UC-02 — Respond to Mentorship Request
| Field | Detail |
|-------|--------|
| Actor | Senior student, alumnus or faculty mentor |
| Related | FR-07 · US-06 |
| Precondition | Mentor is logged in and has expertise tags |
| Postcondition | Request status is *Responded*; student is notified |

**Main flow:** Mentor opens *Requests* → system lists open requests matching expertise → mentor opens a request → mentor submits a response → system updates the status and notifies the student.
**Exception flows:** E1: request already *Resolved* or *Closed* → view only. E2: empty response → blocked.

## UC-03 — Share Resource
| Field | Detail |
|-------|--------|
| Actor | Alumnus or student (faculty assumed) |
| Related | FR-08 · US-03 |
| Precondition | Alumnus is logged in |
| Postcondition | Resource is visible to students with source and category |

**Main flow:** Alumnus or student selects *Share Resource* → enters title, description, category and file/link → submits → system validates and publishes.
**Exception flows:** E1: missing title or category → blocked. E2: non-owner edit or delete → denied (BR-03).

## UC-04 — Publish Event
| Field | Detail |
|-------|--------|
| Actor | Event organizer (primary), Administrator (secondary) |
| Related | FR-10, FR-14 · US-05, US-11 |
| Precondition | Organizer is authorized |
| Postcondition | Event is on the event board |

**Main flow:** Organizer selects *Create Event* → enters title, description, date, time, category → publishes → system displays it to students.
**Alternate flow:** A1: organizer not yet authorized → request goes to the administrator for approval (FR-14). *Build note: not implemented. Any logged-in user can create events (see CR-02).*
**Exception flows:** E1: required fields missing → blocked. E2: unauthorized user → denied (BR-04).

## UC-05 — Screen and Moderate Post  *(implemented)*
| Field | Detail |
|-------|--------|
| Actor | Student/Alumnus (post author), Administrator |
| Related | FR-11, FR-12 · US-08, US-09 |
| Precondition | User is logged in |
| Postcondition | Post is published or blocked; outcome is logged |

**Main flow**
1. User submits a post.
2. System sends the text to the AI classifier and checks toxicity, profanity and insults.
3. Post is within thresholds → system publishes it and classifies it into an academic community.
4. Any user reports the post → it is flagged for administrator review.
5. Administrator manually reviews the post and removes it or dismisses the report.
6. System records the outcome in the moderation log.

**Alternate flow**
- A1: Post exceeds thresholds at step 3 → system blocks it, notifies the user and logs the outcome.

**Exception flows**
- E1: Classifier unavailable → *to confirm* (post is held or published; rule not defined).
- E2: Non-administrator tries to access the review queue → denied (NFR-04).

See [Content-Moderation-Process.md](Content-Moderation-Process.md) for the process flow.
