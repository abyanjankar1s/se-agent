# Project Brief: ResearchFlow

## What we want

Build ResearchFlow, a web-based clinical research recruitment analytics platform for research coordinators, principal investigators, and administrators. The application will centralize synthetic recruitment records and help research teams monitor screening outcomes, enrollment progress, and recruitment performance.

## Users

- **Research Coordinators:** Enter and update recruitment records, import CSV files, and monitor screening progress daily.
- **Principal Investigators:** Review study dashboards and recruitment reports weekly.
- **Administrators:** Manage studies and user access as needed.

The application will run in modern desktop browsers, with responsive layouts and keyboard-accessible forms.

## Must do

1. Authenticate users and restrict study access according to assigned roles.
2. Allow administrators to create, edit, activate, and close research studies with enrollment targets.
3. Allow coordinators to manually add and update synthetic participant recruitment records.
4. Prevent duplicate participant applications within the same study.
5. Import synthetic recruitment records from CSV, validate required fields, and report rejected rows with reasons.
6. Track application statuses: Applied, Screening, Eligible, Ineligible, Enrolled, and Withdrawn.
7. Reject invalid status transitions and record valid changes with timestamps.
8. Record screening outcomes and structured exclusion reasons.
9. Calculate total applications, screening rate, eligibility rate, enrollment conversion, and enrollment progress.
10. Display recruitment funnel and enrollment trend charts, filterable by study and date range.
11. Export aggregate recruitment summaries as CSV.

## Should do

- Compare recruitment performance across multiple studies.
- Display recruitment metrics by source (website, referral, social media).
- Highlight studies falling behind enrollment targets.
- Maintain an audit log of important record changes.

## Constraints

- **Platform / technology:** React, TypeScript, Tailwind CSS, Node.js, Express, PostgreSQL, and Prisma.
- **Data:** Use synthetic participant information only. Store records in PostgreSQL. No real patient or protected health information.
- **Cost:** Use free, locally runnable development tools; no paid APIs or AI services required.
- **Accessibility / privacy / legal:** Keyboard-accessible interfaces, labeled forms, server-side authorization, and no production clinical use.
- **Development:** Git/GitHub for version control, documented setup instructions, and reproducible test data.

## Out of scope (so nobody builds it by accident)

Real patient records, EHR/FHIR integration, AI-based eligibility decisions, recruitment prediction, electronic informed consent, live notifications, and external clinical research integrations.

## Quality expectations

- Separate frontend, API, business logic, and database layers.
- Validate user inputs and enforce database constraints.
- Unit-test recruitment metrics and workflow rules.
- Integration-test authentication, CSV import, and database operations.
- Provide a README with setup, testing, and execution instructions.
- Aim for at least 80% statement coverage of core business logic.

## Acceptance criteria

1. An administrator creates a study with a recruitment target, and an assigned coordinator can access it while an unauthorized user cannot.
2. A coordinator manually adds a participant application; submitting the same participant to the same study again produces an error without creating a duplicate.
3. Importing a CSV containing valid and invalid rows saves valid records and reports rejected rows with specific reasons.
4. Changing a participant from Applied to Screening succeeds and records a timestamp; attempting an invalid transition is rejected.
5. The dashboard displays correct recruitment totals, conversion rates, and enrollment progress from stored synthetic records, and an authorized user can export the aggregate results.

## Open questions

- How many team members will develop the application, and who will own each module?
- What is the final project deadline?
- Should the first version support multiple studies simultaneously or focus on one study?
- Will deployment be required, or is a locally running application sufficient?
