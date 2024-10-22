This High Level Diagram represents the architecture of CareConnect360 and the relationships between different components, helping to understand how the application is structured and how data flows within it.

```mermaid

flowchart TD
    %% User Interface
    subgraph UserInterface[User Interface]
        UI[User Interface]
    end

    %% Frontend
    subgraph Frontend[Frontend]
        FE[React.js Web Application]
        EC2[Apache EC2]
    end

    %% Backend
    subgraph Backend[Backend]
        BE[Node.js & Express.js Server]
        DB[MariaDB Database]
        API[RESTful APIs]
    end

    %% Telehealth Integration
    subgraph Telehealth[Telehealth Integration]
        WebRTC[WebRTC for Video Conferencing]
        SocketIO[Socket.IO for Real-time Communication]
    end

    %% Flow Connections
    UI --> FE
    FE --> EC2
    EC2 --> BE
    BE --> DB
    BE --> API
    BE --> WebRTC
    BE --> SocketIO

    %% Data Flow
    DB -->|Store/Retrieve Patient Records| BE
    API -->|Communicates with External Services| BE
