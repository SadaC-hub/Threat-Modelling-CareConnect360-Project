# Threat-Modelling-CareConnect360-Project

# Threat Modelling Workshop Summary



## Introduction

A 3 Hour threat modelling workshop took place to detail the runbook scenario of multiple attacks against the web-facing health care application Solaris Care Connect 360.



## Attendees

Care Connect Eng team (CodeCare Innovators), Product Managers, DevEx Engineers and the DevSecOps Team.



## Scope

3 Scenarios were run covering: (1) Cross Site Scripting Attack, (2) Insider Threat Attack and (3) API Exploitation Attack



## Methodology

All scenarios were run against the cyber attack kill chain, utilising the Mitre Att&ack framework and STRIDE for control gap assessments. Culminating in identified risks. 



## Conclusion

A total of 4 high risks and 1 medium risks were found during the threat modelling workshop.



## Controls Required



- **HTTPOnly Cookies**: Use HTTPOnly cookies to protect sensitive session data from being accessed by client-side scripts.

- **AWS CloudFront with HTTPS**: Enforce HTTPS with AWS CloudFront to ensure secure communication and data transmission between clients and servers.

- **Content Security Policy (CSP)**: Implement a strong CSP to prevent the loading of unauthorized or malicious resources, reducing the risk of cross-site scripting (XSS).

- **Amazon Cognito with SSO**: Utilize Amazon Cognito for secure user authentication and Single Sign-On (SSO), ensuring user identity management and authentication.

- **AWS IAM for RBAC and Least Privilege**: Leverage AWS IAM to implement Role-Based Access Control (RBAC) and enforce the least privilege principle, granting users only the access they need.

- **Monitoring via AWS GuardDuty and CloudWatch**: Use AWS GuardDuty and Amazon CloudWatch to continuously monitor the system for suspicious activities, unauthorized access attempts, and anomalies in API usage.

- **Auditing with AWS CloudTrail**: Enable AWS CloudTrail to log and audit all API and user activity for visibility into potential unauthorized actions and compliance monitoring.

- **AWS Secrets Manager for Credential Security**: Securely store and automatically rotate sensitive credentials (e.g., API keys, database passwords) using AWS Secrets Manager.

- **AWS Key Management Service (KMS)**: Utilize AWS KMS to encrypt sensitive data, ensuring secure data storage and protection at rest.

- **API Management with AWS API Gateway**: Use AWS API Gateway to manage and secure API requests, enforce rate limiting, and prevent API exploitation.

- **Input Validation**: Implement input validation to ensure that user inputs are properly sanitized, reducing the risk of injection attacks.


# Threat Modelling Process Summary
```mermaid

mindmap
  root((Attack Begins))
    STRIDE/ MITRE ATT CK/ Kill Chain
      Conduct Inherent Risk Assessment
      Create Critical Asset List
        Schedule and Scope Threat Modelling Workshop
    Controls Required
      Risks and Mitigations
      Risk Summary
        Remediation workflow
          Slack
          JIRA
    ATTACK SCENARIOS
      Cross Site Scripting Attack
      Insider Threat Attack
      API Exploitation Attack
      

