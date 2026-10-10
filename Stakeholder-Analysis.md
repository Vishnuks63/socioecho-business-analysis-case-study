# Stakeholder Analysis

## Stakeholder Register

| Stakeholder | Need / Interest | Expected Interaction | Influence | Interest | Engagement Approach |
|-------------|-----------------|----------------------|-----------|----------|---------------------|
| Students | Guidance, mentorship, resources, opportunities | Create requests, connect, access resources and sessions | Medium | High | Involve in requirement validation and UAT |
| Senior Students | Help juniors, receive placement guidance | Connect, respond to requests, mentor | Medium | High | Involve; gather mentor-side needs |
| Alumni | Share experience efficiently with limited time | Respond to requests, share resources, mentor | High | Medium | Consult; keep effort per response low |
| Faculty / College Mentors | Provide academic guidance and information | Share guidance/resources, participate in mentorship | High | Medium | Consult; seek approval on policies |
| Event Organizers | Reach students with relevant opportunities | Publish events/opportunities | Low | High | Inform; confirm authorization process |
| Platform Administrator *(added)* | Keep content appropriate, manage the platform | Manually review flagged/reported posts, remove inappropriate content | High | High | Collaborate on FR-11 and access rules |

**Power-Interest summary:** Manage closely: Administrator, Faculty, Alumni. Keep informed and involved: Students, Seniors, Organizers.

## Elicitation Examples

**Student**
- Problem: May not know whom to approach for specific guidance.
- Need: Communicate the guidance area and discover suitable seniors/alumni.

**Alumnus**
- Problem: Does not know which students need help; limited time for individual responses.
- Need: Visibility into relevant requests and a centralized resource-sharing mechanism.

**Administrator**
- Problem: No control over inappropriate content or unauthorized postings.
- Need: Moderation tools and an approval step for organizers.

## Elicitation Method and Assumptions

This is a self-directed case study based on SocioEcho, a team project built during my final year of B.Tech. No formal interviews or surveys were conducted. Stakeholder needs were identified as follows:

| Stakeholder | Source of understanding | Confidence |
|-------------|-------------------------|------------|
| Students | My own experience as a fresher, and as a final-year student | High (first-hand) |
| Senior students and alumni | Assumptions based on my experience of seeking guidance, supported by online research | Medium (assumed) |
| Faculty | Assumption: faculty already share resources through tools like Google Classroom, so they could also share them on SocioEcho | Medium (assumed) |
| Event organizers | Assumption: a central event board would help them reach students | Medium (assumed) |
| Administrator | Requirements decided by my project team for SocioEcho (moderation and platform administration) | High (team-defined) |

**Roles in the built system:** SocioEcho supports Student and Alumni sign-up roles (seniors are students), plus an Administrator who manually reviews flagged posts. Faculty participation is an assumption and was not built as a role. Any user can create events; restricting this to organizers is a recommended improvement (see CR-02).

**Limitation:** The senior, alumni, faculty and organizer needs are assumptions and would need validation through interviews or surveys before being treated as confirmed requirements. In a real project, these assumptions would be the first thing to validate with stakeholders.

## BA Approach
Stakeholder needs were translated into business objectives (BO), functional requirements (FR), user stories (US), use cases (UC) and testable acceptance criteria, all linked in the [RTM](Requirements-Traceability-Matrix.md).
