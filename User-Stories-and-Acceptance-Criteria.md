# User Stories and Acceptance Criteria

Priority uses MoSCoW. Stories US-06 to US-12 are **new** and close traceability gaps. **Build status** shows what the SocioEcho final-year project implemented.

---
### US-01 — Connect with relevant seniors and alumni  |  Must  |  FR-02, FR-04
**Build status:** Partially implemented. Users can follow others and find users by unique ID. Search by skill/expertise and connection approval are not implemented.
**As a** student, **I want to** connect with relevant seniors and alumni **so that** I can get guidance on academics, placements, projects and careers.

- **AC1** Given I am logged in, when I search by skill or category, then I see matching seniors/alumni with name, role and expertise.
- **AC2** Given I view a profile, when I select Connect, then a request is sent and the status shows *Pending*.
- **AC3** Given the mentor accepts or declines, when I open my connections, then the status shows *Connected* or *Declined*.
- **AC4** Given no one matches my search, then I see a "no results" message with a suggestion to broaden the search.

### US-02 — Create a mentorship request  |  Must  |  FR-05, FR-06
**Build status:** Implemented as task-based mentorship rooms, where a student books mentorship help. Exact request fields (such as a category) to confirm.
**As a** student, **I want to** create a mentorship request for the area where I need guidance **so that** a suitable senior or alumnus can help.

- **AC1** Given I am logged in, when I choose a category (Academic, Placement, Project, Career), enter details and submit, then the request is saved as *Open* and I see a confirmation.
- **AC2** Given I leave the category or details empty, when I submit, then submission is blocked and the missing fields are highlighted (BR-01).
- **AC3** Given a mentor has responded, when I open *My Requests*, then I can see the response and who responded.

### US-03 — Share relevant resources  |  Must  |  FR-08
**Build status:** Implemented (Resource Library). Student and Alumni logins can share resources; faculty is not a separate role.
**As an** alumnus, student or faculty member, **I want to** share academic and career resources **so that** I can help many students without answering each one individually.

- **AC1** Given I am an alumnus, when I upload a resource with title, description and category, then it is published with its source and category visible to students.
- **AC2** Given I leave the title or category empty, then upload is blocked.
- **AC3** Given I am not the owner or an administrator, when I try to edit or delete a resource, then access is denied (BR-03).

### US-04 — Conduct mentorship sessions  |  Should  |  FR-09
**Build status:** Implemented (AMA Session page). Access rules and participant limits to be confirmed.
**As a** student, **I want to** join mentorship sessions with seniors and alumni **so that** I can get detailed guidance through discussion.

- **AC1** Given I am an eligible user, when I create a session with topic, date/time and participant limit, then it is created and listed.
- **AC2** Given I am an authorized participant, when I join, then I can take part; given I am not authorized, then access is denied.
- **AC3** Given I am the session organizer, when I close the session, then no further messages can be posted.

*Open question OQ-02: confirm whether sessions use text chat, video, or both.*

### US-05 — Publish events and opportunities  |  Should  |  FR-10
**Build status:** Partially implemented. The Event Board works, but any logged-in user can create events, so AC3 is not met. See CR-02.
**As an** authorized event organizer, **I want to** publish college events and opportunities **so that** students can discover them.

- **AC1** Given I am an authorized organizer, when I enter title, description, date, time and category and publish, then the event appears on the event board.
- **AC2** Given I am a student, when I open the event board, then I can view the list and each event's details.
- **AC3** Given I am not an authorized organizer, when I try to create, edit or remove an event, then access is denied (BR-04).

### US-06 — Respond to mentorship requests  |  Must  |  FR-07  **(new)**
**Build status:** Partially implemented. Mentors respond through mentorship rooms and threaded replies. Requests are not matched to mentor expertise; the accept/decline flow is to confirm.
**As a** senior or alumnus, **I want to** view open requests that match my expertise and respond **so that** I can help the students who need it.

- **AC1** Given I have expertise tags, when I open *Requests*, then I see open requests whose category matches my expertise.
- **AC2** Given I submit a response, then the request status changes to *Responded* and the student is notified.
- **AC3** Given a request is *Resolved* or *Closed*, then I can view it but cannot respond.

### US-07 — Receive mentor and resource recommendations  |  Should  |  FR-01, FR-02, FR-03  **(new)**
**Build status:** Not implemented. Listed as future scope. A non-personalised panel of available communities and popular users exists.
**As a** student, **I want to** receive recommended mentors and resources after submitting a request **so that** I can get help faster.

- **AC1** Given I submit a request with a category, then the system shows recommended mentors and resources for that category.
- **AC2** Given no mentor matches, then the request stays *Open* and relevant resources are shown (see exception flow).

*Open question OQ-03: ranking rule when several mentors match.*

### US-08 — Review reported content and remove inappropriate posts  |  Must  |  FR-11
**Build status:** Implemented for posts. Resource Library moderation is future scope.
**As an** administrator, **I want to** manually review flagged and reported posts and remove inappropriate ones **so that** the platform stays safe and academic.

- **AC1** Given any user reports a post, then it is flagged for administrator review.
- **AC2** Given I am an administrator, when I remove a reported post, then it is no longer visible and the action is recorded in the moderation log.
- **AC3** Given I dismiss a report, then the post stays visible and the report is closed.
- **AC4** Given I am not an administrator, then I cannot access moderation functions (NFR-04).

### US-09 — Screen posts before publication  |  Must  |  FR-12  **(new)**
**Build status:** Implemented (BART-large-MNLI classifier).
**As a** student or alumnus, **I want** my posts screened before they are published **so that** discussions stay free of toxic content.

- **AC1** Given I submit a clean academic post, when screening passes, then it is published and classified into an academic community.
- **AC2** Given my post exceeds the toxicity, profanity or insult threshold, then it is blocked and I am told it was not published.
- **AC3** Given any post is screened, then the outcome is recorded in the moderation log.
- **AC4** *(Future scope)* Given a document is uploaded to the Resource Library, then it is also screened.

### US-10 — Register with a role and log in securely  |  Must  |  FR-13  **(new)**
**Build status:** Implemented (JWT sessions, bcrypt password hashing, suspicious-login detection).
**As a** new user, **I want to** sign up as a student or alumnus and log in securely **so that** only verified members access the platform.

- **AC1** Given I choose the Student or Alumni role, then I am asked for the details for that role.
- **AC2** Given valid credentials, when I log in, then I receive a session token and can use the platform.
- **AC3** Given I am not logged in, then protected features are not accessible.
- **AC4** Given a login from a new device or IP address, then it is checked as a possible suspicious login.

### US-11 — Authorize event organizers  |  Should  |  FR-14  **(new)**
**Build status:** Not implemented. Any user can currently create events. Recommended improvement (CR-02).
**As an** administrator, **I want to** approve event organizers **so that** only authorized people publish events.

- **AC1** Given I am an administrator, when I approve an organizer, then that user can publish events.
- **AC2** Given a user is not approved, then they cannot publish events (BR-04).

### US-12 — Track mentorship progress with tasks  |  Should  |  FR-15  **(new)**
**Build status:** Implemented (task-based mentorship rooms). *Acceptance criteria are drafted from the feature description and should be checked against the build.*
**As a** student, **I want to** track my mentorship progress through tasks **so that** guidance turns into action.

- **AC1** Given I have a mentorship room, when a task is added, then it appears in the room's task list.
- **AC2** Given a task is completed, then its status updates and my progress is visible.
- **AC3** Given I am not a participant in the room, then I cannot view or change its tasks (NFR-04).
