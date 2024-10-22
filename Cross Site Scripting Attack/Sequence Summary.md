# Summary MITRE ATT&CK Sequence

### Attack Description

Cross-Site Scripting (XSS) is a type of security vulnerability found in web applications that allows attackers to inject malicious scripts into content delivered to users. By exploiting this vulnerability, an attacker can execute arbitrary JavaScript in the victim's browser, compromising the integrity and confidentiality of the user's data.


### Methodology

The attack sequence below utilises the MITRE ATT&CK framework along with the commonly used techniques. 

```mermaid

flowchart TD

    A[User Interaction] --> B{Reconnaissance}
    
    B -->|Identify vulnerable input fields| C[Identify Target]
    
    C -->|Analyze application behavior| D[Research Application]

    D -->|Craft malicious JavaScript payload| E[Weaponization]

    E -->|Deliver payload via phishing email| F[Delivery]

    F -->|User clicks malicious link| G[Execution]

    G -->|Execute script in user’s browser| H[Exploitation]

    H -->|Steal session cookies or tokens| I[Credential Access]

    H -->|Manipulate DOM for input capture| J[User Manipulation]

    I -->|Gains unauthorized access| K[Initial Access]

    J -->|Redirect user to fraudulent site| L[Social Engineering]

    K -->|Access sensitive data| M[Data Exfiltration]

    L -->|Collect sensitive user information| N[Credential Theft]

    M -->|Achieve objectives| O[Actions on Objectives]

