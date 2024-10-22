# Summary MITRE ATT&CK Sequence

### Attack Description

An insider threat occurs when a current or former employee, contractor, or business partner with inside information about an organization’s security practices, data, and computer systems misuses their access to confidential information. This can lead to data breaches, unauthorized access, and other malicious activities.

### Methodology

The attack sequence below utilizes the MITRE ATT&CK framework along with the commonly used techniques. 

```mermaid
flowchart TD

    A[User Interaction] --> B{Reconnaissance}
    
    B -->|Identify weaknesses in access controls| C[Identify Target]
    
    C -->|Analyze security measures| D[Research Application]

    D -->|Develop plan to misuse access| E[Weaponization]

    E -->|Deliver sensitive information via internal email| F[Delivery]

    F -->|Manipulate colleague to disclose data| G[Execution]

    G -->|Exploit privileged access| H[Exploitation]

    H -->|Steal sensitive data such as PHI| I[Data Exfiltration]

    H -->|Manipulate records or data| J[Data Manipulation]

    I -->|Gain unauthorized access to accounts| K[Unauthorized Access]

    J -->|Cause operational disruption| L[Service Disruption]

    K -->|Access sensitive data| M[Data Breach]

    L -->|Collect sensitive user information| N[Credential Theft]

    M -->|Achieve malicious objectives| O[Actions on Objectives]
