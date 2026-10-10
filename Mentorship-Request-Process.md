# Process Mapping — Mentorship Request

## To-Be Process Flow

```mermaid
flowchart TD
    subgraph Student
        A["Identify guidance need"] --> B["Log in to SocioEcho"]
        B --> C["Create request: category and details"]
    end
    C --> D{"Valid?"}
    D -- No --> C
    D -- Yes --> E["System saves request, status Open"]
    subgraph System
        E --> F["Identify topics, match mentors and resources"]
        F --> G{"Suitable mentor found?"}
    end
    G -- Yes --> H["Notify relevant seniors/alumni"]
    G -- No --> I["Keep request Open, show relevant resources"]
    I --> P["Re-match when new mentor or resource is available"]
    P --> F
    subgraph Mentor
        H --> J["View request"]
        J --> K["Respond or accept"]
    end
    K --> L["Student notified of response"]
    L --> M{"Issue resolved?"}
    M -- Yes --> N["Request marked Resolved"]
    M -- No --> O["Follow-up or mentorship session"]
    O --> L
```

## Primary Flow
1. Student identifies a guidance need and logs in.
2. Student creates a request with category and details (BR-01).
3. System validates and saves the request as **Open**.
4. System identifies topics and recommends relevant mentors and resources (FR-01 to FR-03).
5. Relevant seniors/alumni are notified and view the request (FR-07).
6. A mentor responds; the student is notified.
7. If resolved, the request is marked **Resolved**; otherwise the conversation continues through follow-up or a mentorship session (FR-09).

## Exception Flow: No Suitable Mentor
The request stays **Open**, the student is shown relevant resources, and the system re-matches when new mentors or resources become available. *The exact rule for an unmatched request (for example, how long it stays open) must be confirmed with stakeholders (OQ-01).*

## Request Status Lifecycle
`Open → Responded → Resolved` (or `Closed` if withdrawn or expired)

## Process Analysis
The flow separates the student's need, submission, matching, response and resolution into distinct steps. This gives a basis for requirement validation, measuring response time and resolution rate (BO-03, BO-04), and later change-impact analysis.
