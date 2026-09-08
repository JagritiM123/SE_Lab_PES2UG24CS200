# Lab 3 — Component Modelling & Architectural Pattern Selection

**Scenario:** Patient Health Record Consent Management System


## Architecture Selected

**Microservices** — chosen over Layered and Client-Server because consent decisions, authentication, audit logging, and notifications each carry different sensitivity and compliance needs, and each must be able to scale and fail independently without compromising the consent-check path.

## Components (7)

1. Patient Portal UI
2. Authentication & Authorization Service
3. Consent Management Service
4. Health Record Access Service
5. Audit Logging Service
6. Notification Service
7. Consent Database

## Key Interfaces

- `Patient Portal UI → AuthAPI / ConsentAPI`
- `Consent Management Service → AuthAPI / AuditAPI / NotificationAPI / ConsentDataAPI`
- `Health Record Access Service → ConsentAPI` (the enforcement point — no record is released without a live consent check)

See `Lab3_Patient_Consent_Report.docx` for full justification and interface details.
