## Git Workflow:
I followed a typical Git workflow for making and managing changes to the project:
- Forked the repository to my GitHub account.
- Created a new branch for my changes.
- Made changes to the Dockerfiles, docker-compose.yml, and any other necessary files.
- Committed my changes with clear and descriptive commit messages.
- followed the Git feature branch workflow for development. Features or fixes were developed on separate branches, then merged into the main branch via pull requests after code review and testing.

## Base Image Selection:
1. **Client**: For the web application component, I chose the official Node:14-alpine base image. 

2. **Backend**: For the web application component, I chose the official Node:14-alpine base image.   

## Dockerfile :
1. **Client & backend**: The Dockerfile for the web application installs dependencies using npm and copies the application code into the container. It then exposes the necessary port for communication with the outside world and specifies the command to start the application.
2. **Database**: The Dockerfile for MongoDB simply uses the official image without any additional customization since it provides all the necessary functionality out of the box.

## Docker Compose Networking:

I used the default bridge network provided by Docker Compose for communication between the web application and the MongoDB database. This allows the services to communicate with each other using their service names as hostnames.

## Docker Compose Volume Definition and Usage:

I defined a volume for the MongoDB service to ensure persistence of data. This volume is mounted to a directory within the MongoDB container where the database stores its data. This ensures that data added to the database persists even if the container is stopped or restarted.

**Kubernetes Deployment**:
   - I opted to use Deployment objects for managing our application's deployment. Deployments are suitable for stateless applications, allowing for easy scaling and rolling updates.
   - For storage solutions, we chose to use StatefulSets where state persistence is crucial. StatefulSets offer stable, unique network identifiers and stable storage, which is essential for applications requiring persistent storage.

**Good Practices for Docker Image Tag Naming**:
   - We adhered to Docker image tag naming standards for ease of identification and personalization of images and containers. Tags were versioned using semantic versioning (e.g., `v1.1.2`) and included relevant information such as build numbers or commit hashes for traceability.
