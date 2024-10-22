| Category             | Description                                                   | Likelihood | Impact | Risk Rating | Scenario                                    |
|----------------------|---------------------------------------------------------------|------------|--------|-------------|---------------------------------------------|
| Data                 | Lack of WAF and input validation, allowing XSS attacks       | High       | High   | High        | User credentials compromised via XSS       |
| Data                 | Insider threat due to insufficient access controls (RBAC)    | High       | High   | High        | Unauthorized access to sensitive patient data |
| API                  | API endpoints vulnerable to DoS attacks due to lack of rate limiting | Medium     | High   | High        | Service disruption from API DoS attack     |
| API                  | Insufficient logging and monitoring of API calls              | Medium     | High   | High        | API exploitation attempts go undetected    |
| Data                 | Sensitive data exposed due to lack of encryption              | High       | High   | High        | Data breach leading to patient information leak |
| Data                 | Weak authentication mechanisms allowing credential abuse       | High       | High   | High        | Insider stealing patient information         |
| API                  | Lack of API management leading to exploitation of unprotected endpoints | High       | High   | High        | Attackers leveraging unprotected APIs       |
| Data                 | Absence of content security policy increases XSS risk        | High       | Medium | High        | Increase in XSS vulnerabilities in the application |
