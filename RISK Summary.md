# Risk Summary: All Three Attacks

## Cross Site Scripting (XXS)

| Risk ID | Risk                                                    | Score  | Impact | Likelihood | Mitigation Plan                                                              |
|---------|----------------------------------------------------------|--------|--------|------------|------------------------------------------------------------------------------|
| R1      | No WAF at the front end; risk of script injection (XSS)  | High   | High   | High       | Implement AWS WAF with custom rules to block malicious XSS patterns           |
| R2      | Lack of input validation in React.js; potential XSS      | Medium | Medium | Medium     | Ensure input validation via Lambda security controls                         |
| R3      | No HTTPOnly cookies; risk of session hijacking           | High   | Medium | High       | Implement HTTPOnly cookies to protect client-side scripts from access        |
| R4      | No content security policy; increased XSS vulnerability  | Medium | High   | Medium     | Enable HTTPS with AWS CloudFront and set up content security policy          |



## Insider Threat Attack 

| Risk ID | Risk                                                      | Score  | Impact | Likelihood | Mitigation Plan                                                      |
|---------|------------------------------------------------------------|--------|--------|------------|----------------------------------------------------------------------|
| R5      | Lack of RBAC and least privilege access control            | High   | High   | Medium     | Implement custom access rules via AWS IAM to enforce least privilege |
| R6      | No auditing/logging controls for insider attack detection   | High   | High   | High       | Enable AWS CloudTrail for auditing and logging suspicious activities  |
| R7      | No monitoring controls to flag suspicious behavior         | High   | High   | Medium     | Use AWS GuardDuty to detect anomalies and unusual behavior patterns   |
| R8      | No system to detect unauthorized data changes              | High   | Medium | Medium     | Add Amazon CloudWatch to monitor and alarm on suspicious activities   |
| R9      | Insider can exploit exposed API keys and credentials       | High   | High   | High       | Use AWS Secrets Manager for regular credential rotation               |
| R10     | No encryption for sensitive data at rest in the database   | High   | High   | Low        | Implement AWS KMS for encrypting data at rest and in transit          |



## API Exploitation Attack

| Risk ID | Risk                                                      | Score  | Impact | Likelihood | Mitigation Plan                                                      |
|---------|------------------------------------------------------------|--------|--------|------------|----------------------------------------------------------------------|
| R11     | No API management tool in place, vulnerable to DoS attacks | Medium | Medium | Medium     | Implement API Gateway with rate limiting and throttling to prevent DoS |
| R12     | No input validation for API calls in Lambda                | Medium | Medium | Medium     | Add input validation in AWS Lambda functions to ensure safe data processing |
| R13     | Lack of security layers on API Gateway, vulnerable to attacks | High   | High   | High       | Integrate AWS WAF with API Gateway to protect against SQLi, XSS, etc. |
| R14     | No logging for API calls to detect suspicious activity      | Medium | Medium | Medium     | Use Amazon CloudWatch to monitor and alert unusual API access patterns |
| R15     | No management of API credentials, risk of hard-coded keys  | High   | High   | Low        | Implement AWS Secrets Manager to regularly rotate and manage API credentials |
