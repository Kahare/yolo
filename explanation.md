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

## Git Workflow:

I followed a typical Git workflow for making and managing changes to the project:
- Forked the repository to my GitHub account.
- Created a new branch for my changes.
- Made changes to the Dockerfiles, docker-compose.yml, and any other necessary files.
- Committed my changes with clear and descriptive commit messages.
- Pushed the branch to GitHub and submitted a pull request for review.

## Testing and Debugging:

I tested the containerized application locally using Docker Compose. I am unable to verify that the web application functions correctly and that data persistence works as expected. I was unable to debugged any issues that arose during testing.

## Deployment:

Once satisfied with my changes and testing, I pushed the changes to GitHub. Automated builds were set up on Docker Hub to automatically build and push Docker images for the project. A screenshot of the deployed image on Docker Hub, clearly indicating the version of the image, is provided in the repository.

