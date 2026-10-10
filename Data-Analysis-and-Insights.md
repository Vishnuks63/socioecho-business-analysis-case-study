# Basic Data Analysis

## Purpose
Demonstrate routine descriptive analysis on simulated mentorship-request data.

> **Important:** The dataset is simulated sample data, generated with an AI assistant for this portfolio case study. It is not real SocioEcho user data.

## Questions Analyzed
1. Which category has the highest number of requests?
2. What is the average response time?
3. What percentage of requests were resolved?
4. Which mentor type handled the most requests?

## Findings

| Measure | Result |
|---------|--------|
| Total requests analyzed | 30 |
| Most requested category | Placement |
| Average response time | 18.97 hours |
| Resolution rate | 80% (24 of 30 resolved, 6 unresolved) |
| Most active mentor type | Alumni |

## Method
The simulated dataset was imported into Power BI, where counts, averages and percentages were calculated and the distribution of requests by category was visualized. A fuller dashboard is in the separate SocioEcho Mentorship Analytics Dashboard project.

## BA Interpretation
- Placement guidance is the largest demand area, so curated placement resources are a priority (supports FR-03, FR-08).
- An average of about 19 hours is within a 24-hour target, but an average can hide slow cases. Median response time and the share of requests answered within 24 hours would be better service measures (BO-03).
- Six unresolved requests (20%) should be broken down by category and mentor type to find the cause (matching, availability or request quality).

## Limitations
The dataset has only 30 simulated records, so results are illustrative and not statistically meaningful.

## Recommended Next Steps
1. Add median and "% within 24 hours" for response time.
2. Break down resolution rate by category and mentor type.
3. Track these as KPIs in the Power BI dashboard.

## Files
- `socioecho_mentorship_requests_simulated.csv`
- `socioecho_request_categories.png`
