# CoWrite
A web based collaborative editor built with CRDTs.

# Stack

This project is a web-based collaborative editor built with 
- Frontend - React.js
- Backend - Golang
- Deployment - Cloud platform
- Containerization - Docker
- Monitoring - Prometheus

## Features

- **Private Rooms**: Participants can join through a link, similar to Google Docs, where access can be requested via email.
- **Workspaces Handling Multiple Files**: Each user has access to a personal store wherefrom, storage and retrieval of files will be possible.
- **Highly Minimalistic and Modern UI**: The user interface is designed to be simple and modern for an optimal user experience.

## Architectural diagram
![image](https://github.com/oceakun/CoWrite/assets/83641627/9a7a2e94-dd3e-475f-ac0d-1b5fb852e7a2)


## Architecture Overview

The collaborative editor follows a client-server architecture, where the frontend and backend work together to enable real-time collaboration on documents.

### Frontend

The frontend of the collaborative editor is built using React.js, a popular JavaScript library for building user interfaces. The primary responsibility of the frontend is to provide a user-friendly interface for editing documents and to handle real-time updates.

#### Functionality:

1. **Markdown Editing Interface**: Utilizing the `react-md-editor` library, the frontend provides an intuitive interface for users to edit documents using Markdown syntax.

2. **Real-time Communication**: Every edit made by a user on the frontend is communicated to the backend in real-time using WebSocket technology. This ensures that changes are immediately propagated to other users viewing the same document.

3. **Conflict Resolution**: In case of concurrent edits by multiple users, the frontend communicates with the backend to resolve conflicts using Conflict-Free Replicated Data Types (CRDTs). CRDTs ensure that all versions of the document converge to a consistent state, even in the presence of concurrent edits.

### Backend

The backend of the collaborative editor is built using Golang, a statically typed and compiled programming language known for its performance and simplicity. It handles the business logic, data processing, and communication with the frontend.

#### Functionality:

1. **WebSocket Server**: The backend includes a WebSocket server that receives edit requests from the frontend and broadcasts them to all connected clients in real-time.

2. **Conflict Resolution with CRDTs**: Upon receiving edit requests, the backend utilizes a system built with Conflict-Free Replicated Data Types (CRDTs) to resolve conflicts. CRDTs ensure that all clients reach a convergent state without requiring centralized coordination or locking mechanisms.

3. **Persistence**: The backend is responsible for persisting document data to a database, ensuring that changes are preserved even if the server restarts or crashes.

# Project Timeline(15 May to 15 July ~ 56 days)

### Week 1-3: Initial setup and Backend Development
- Project requirements, following features.
- Set up development environments for frontend and backend.
- Set up backend server using Golang.
- Define WebSocket endpoints for communication.
- Develop conflict resolution logic using CRDTs.
- Integrate persistence layer for storing document data.

### Week 4-5: Frontend Development
- Design a minimal UI on Figma.
- Develop following components with React.js:
  - file system
  - private rooms
  - main editor
- Implement markdown editing functionality using `react-md-editor`.
- Set up WebSocket communication for real-time communication with backend.

### Week 6: Deployment
- Deploy the application to cloud using Docker containers.
- Configure CI/CD pipelines for automated testing and deployment.

### Week 7: Testing
- Conduct thorough testing of the entire application.
- Address any critical bugs or issues.

### Week 8: Monitoring integration and Finalization
- Integrate Prometheus
- Finalize project documentation, including README and user guides.


## License
This project is licensed under the [MIT License](LICENSE).
