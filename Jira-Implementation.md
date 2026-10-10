# Jira Implementation

## Purpose
Jira (Scrum) was used as a **learning exercise** to translate the documented requirements into an Agile work structure and to practise how epics, stories and subtasks are organized and tracked. It was not used to run sprints or manage the delivery of the SocioEcho build.

## Work Item Structure

**Epic:** Student-Alumni Mentorship
**Feature:** Student-Senior-Alumni Connections

### Stories in Jira

| Jira Story | Case-Study ID | Requirements | Priority |
|------------|---------------|--------------|----------|
| Connect with relevant seniors and alumni | US-01 | FR-02, FR-04 | Must |
| Create a mentorship request | US-02 | FR-05, FR-06 | Must |
| Share relevant resources with students | US-03 | FR-08 | Must |
| Conduct mentorship sessions | US-04 | FR-09 | Should |
| Publish events and opportunities | US-05 | FR-10 | Should |

Each story was supported by three BA-oriented subtasks covering activities such as requirement definition, acceptance criteria, validation, access rules, process definition and review.

### Stories documented in the case study but not yet created in Jira

| Case-Study ID | Story | Requirements | Build status |
|---------------|-------|--------------|--------------|
| US-06 | Respond to mentorship requests | FR-07 | Partial |
| US-07 | Receive mentor and resource recommendations | FR-01, FR-02, FR-03 | Not implemented |
| US-08 | Review reported content and remove inappropriate posts | FR-11 | Implemented |
| US-09 | Screen posts before publication | FR-12 | Implemented |
| US-10 | Register with a role and log in securely | FR-13 | Implemented |
| US-11 | Authorize event organizers | FR-14 | Not implemented |
| US-12 | Track mentorship progress with tasks | FR-15 | Implemented |

These stories, with their acceptance criteria, are in [User-Stories-and-Acceptance-Criteria.md](User-Stories-and-Acceptance-Criteria.md). In a live project they would be added to the backlog and prioritized with the Must/Should ranking above.

## Traceability
Each Jira story carries the same ID as the case-study user story (US-01 to US-05), so the chain remains traceable:
`Business Objective → Requirement (FR/NFR) → User Story → Use Case → Test Case`
See the [Requirements Traceability Matrix](Requirements-Traceability-Matrix.md).

## Workflow Practiced

**Idea → To Do → In Progress → In Review → Done**

The workflow was used to understand how a discrete BA task progresses from identification through completion and review.

## Change Handling
Change requests are documented in [Change-Impact-Analysis.md](Change-Impact-Analysis.md). In Jira, an approved change (for example CR-01 or CR-02) would update the affected story and its subtasks, and the RTM would be revised to match.

## BA Value
Jira provided practical exposure to organizing requirements into an Agile work hierarchy and tracking discrete analysis tasks through a defined workflow.
