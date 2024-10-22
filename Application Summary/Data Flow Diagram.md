The Data Flow Diagram is used to highlight any key critical areas of the application that will be targeted by a likely attacker.

```mermaid

erDiagram
    %% Sensitive Entities
    PATIENT {
        string id PK "Patient ID"
        string name "Patient Name"
        string medical_history "Medical History"
        string sensitive_data "Sensitive Data (e.g., PII)"
    }
    
    PROVIDER {
        string id PK "Provider ID"
        string name "Provider Name"
        string credentials "Provider Credentials"
        string access_level "Access Level (e.g., RBAC)"
    }
    
    API_CREDENTIALS {
        string id PK "API Credential ID"
        string key "API Key"
        string secret "API Secret"
        string created_at "Creation Date"
        string last_used "Last Used Date"
    }

    MEDICATION {
        string id PK "Medication ID"
        string name "Medication Name"
        string dosage "Dosage"
        string patient_id FK "Patient ID"
    }
    
    TELEHEALTH_SESSION {
        string id PK "Session ID"
        dateTime date "Session Date"
        string patient_id FK "Patient ID"
        string provider_id FK "Provider ID"
        string video_link "Video Link (WebRTC)"
    }

    LOGGING {
        string id PK "Log ID"
        string action "User Action"
        string timestamp "Action Timestamp"
        string user_id FK "User ID"
    }

    %% Relationships
    PATIENT ||--o{ MEDICATION : "takes"
    PROVIDER ||--o{ TELEHEALTH_SESSION : "conducts"
    PATIENT ||--o{ TELEHEALTH_SESSION : "attends"
    PROVIDER ||--o{ API_CREDENTIALS : "uses"
    API_CREDENTIALS ||--o{ LOGGING : "logs access to"
