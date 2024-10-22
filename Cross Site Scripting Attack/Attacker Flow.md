This is a an example of an attacker flow using mermaid.

```mermaid

sequenceDiagram

    participant Attacker
    participant CareConnect360
    participant CnCServer
    participant BackendServer
    participant User

    activate Attacker

    Attacker->>CareConnect360: Identify vulnerable input fields
    CareConnect360->>Attacker: Input fields identified
    deactivate Attacker

    activate Attacker
    Attacker->>CareConnect360: Craft malicious JavaScript payload
    CareConnect360->>Attacker: Payload crafted
    deactivate Attacker

    activate Attacker
    Attacker->>User: Send phishing email with malicious link
    User->>CareConnect360: Clicks on malicious link
    activate User
    CareConnect360->>User: Execute malicious script
    User->>CareConnect360: Send sensitive data (cookies, tokens)
    deactivate User
    deactivate Attacker

    activate Attacker
    Attacker->>BackendServer: Exploit executed via user’s session
    BackendServer->>CnCServer: Communication established
    CnCServer->>BackendServer: Commands issued
    BackendServer->>CnCServer: Actions performed
    deactivate Attacker
