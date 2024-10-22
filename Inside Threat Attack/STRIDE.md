Diagram that reflects the current controls in place for CareConnect360, focusing on mitigating risks associated with Insider Threat Attacks and other relevant security threats using the STRIDE framework.

```mermaid

graph TD

    subgraph User Interaction
        A[User] -->|HTTP Requests| B[Web Server]
    end

    subgraph Web Server
        B -->|Access| C[Database]
        B -->|Receive Input| D[Input Validation]
        B -->|Execute| E[Application Logic]
    end

    subgraph Database
        C -->|Store/Fetch Data| F[Data Storage]
    end

    A((User)) -.->|Authentication| G[Authentication Mechanism]

    B -.->|Logging| H[Logging Service]

    A -.->|Access| I[Admin Panel]
    I -.->|Controls| J[Admin Functionality]

    %% Current Controls in Place

    Control1([Control: Input Sanitization]) --> D
    Control2([Control: Content Security Policy]) --> B
    Control3([Control: JWT Authentication]) --> G
    Control4([Control: HTTPS for Secure Communication]) --> B
    Control5([Control: Secure Cookies - HttpOnly]) --> F
    Control6([Control: Rate Limiting]) --> B
    Control7([Control: Role-Based Access Control]) --> I
    Control8([Control: User Activity Monitoring]) --> H

    %% STRIDE Threats Related to Insider Attacks

    T1([Spoofing: Session Hijacking]) -.-> A
    T2([Tampering: Altering Content]) -.-> B
    T3([Repudiation: Deny Actions Taken]) -.-> H
    T4([Information Disclosure: Sensitive Data Exposure]) -.-> F
    T5([Denial of Service: Overloading Server]) -.-> B
    T6([Elevation of Privilege: Unauthorized Actions]) -.-> I

    %% Mitigations (now controls)

    M1([Control: Input Sanitization]) --> T1
    M2([Control: Content Security Policy]) --> T2
    M3([Control: Logging and Monitoring]) --> T3
    M4([Control: Secure Cookies - HttpOnly]) --> T4
    M5([Control: Rate Limiting]) --> T5
    M6([Control: Role-Based Access Control]) --> T6
    M7([Control: User Activity Monitoring]) --> T1
    M8([Control: Regular Security Audits]) --> T4
