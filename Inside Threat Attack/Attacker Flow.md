This is a an example of an attacker flow using mermaid.

```mermaid

sequenceDiagram

    participant Insider
    participant CareConnect360
    participant CnCServer
    participant BackendServer
    participant User

    activate Insider

    Insider->>CareConnect360: Identify weaknesses in security measures
    CareConnect360->>Insider: Security measures analyzed
    deactivate Insider

    activate Insider
    Insider->>CareConnect360: Develop misuse plan for access rights
    CareConnect360->>Insider: Plan approved
    deactivate Insider

    activate Insider
    Insider->>User: Send misleading internal email
    User->>CareConnect360: Clicks on malicious link
    activate User
    CareConnect360->>User: Execute unauthorized action
    User->>CareConnect360: Sends sensitive data (PHI)
    deactivate User
    deactivate Insider

    activate Insider
    Insider->>BackendServer: Exploit executed through insider access
    BackendServer->>CnCServer: Communication established
    CnCServer->>BackendServer: Commands issued for data extraction
    BackendServer->>CnCServer: Actions completed
    deactivate Insider
