## What is Docker Automation Script for Node Deployment
**build.sh** is a meticulously crafted script designed with a single purpose: to streamline and automate the intricate process of Docker image creation. Serving as the linchpin in your containerization workflow, it simplifies what can otherwise be a complex endeavor — constructing Docker images from source code and configurations becomes effortless.

**run_node.sh** is a versatile gem. Tailored specifically to ease the deployment and operation of validator and provider nodes, this script is your trusted ally. Whether you’re engaged in a proof-of-stake network as a validator or managing vital infrastructure as a node operator, ‘run_node.sh’ simplifies your tasks and enhances your efficiency.

At the heart of Docker’s image-building process lies the Dockerfile, a plain-text configuration file. It serves as your step-by-step guide for creating Docker images that encapsulate all the essentials for running software. From application code to runtime environment, dependencies, and configuration files, the Dockerfile is your blueprint for success.

Enter docker-compose.yml, a YAML-formatted configuration file that takes command in the realm of multi-container Docker environments. Consider it the mission control for orchestrating your application’s containers. With it, you define services, networking, volumes, and other critical elements, enabling you to master the intricacies of your containerized setup effortlessly.

## Install Docker Engine
- [Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- [Debian](https://docs.docker.com/engine/install/debian/)
- [CentOS](https://docs.docker.com/engine/install/centos/)

## Build steps of the artela node
Run build.sh and answer all question:

```bash
username:~/Docker$ ./build.sh
What node type is required for build?
1) node
Node type selected: 1
Enter image name: artela
Enter release tag: v0.4.2-beta
Do you want to send the image to DockerHub?
1) yes
2) no
Send the image to DockerHub: 1
Enter username: svetekllc
Enter password: *********

### The build information ###
Build date:     2023-12-27
Docker context: /opt/docker
Dockerfile:     /opt/docker/Dockerfile
Docker Image:   svetekllc/artela:v0.4.2-beta-node
Node type:      node
Version:        v0.4.2-beta

[+] Building 62.9s (17/17) FINISHED                                     docker:default
 => [internal] load .dockerignore                                                 0.0s
 => => transferring context: 2B                                                   0.0s
 => [internal] load build definition from Dockerfile                              0.0s
 => => transferring dockerfile: 814B                                              0.0s
 => [internal] load metadata for docker.io/library/golang:1.21-bookworm           0.9s
 => [internal] load metadata for docker.io/library/debian:bookworm-slim           0.9s
 => [auth] library/debian:pull token for registry-1.docker.io                     0.0s
 => [auth] library/golang:pull token for registry-1.docker.io                     0.0s
...
 => => naming to docker.io/svetekllc/artela:v0.4.2-beta-node                      0.0s

Sending docker image "svetekllc/artela:v0.4.2-beta-node" to DockerHub

Login Succeeded
The push refers to repository [docker.io/svetekllc/artela]
31cd1e146df2: Pushed
dc913103e118: Pushed
50c97e8fd52e: Pushed
56ac3146fc1c: Pushed
7292cf786aa8: Pushed
v0.4.2-beta-node: digest: sha256:0d5d6f4e47e6fa05bdd5cf4047ac575b61c5be1c24aba4dbf5087c075ea376b7 size: 1368

The build is complete!
```

1. User Interaction: The script starts by prompting the user to select the type of node they want to build. The user selects “1” to indicate that they want to build a provider node.

2. Image Configuration: Next, the user is asked to specify an image name (in this case, “artela”) and a release tag (here, “v0.4.2-beta”).

3. DockerHub Image Upload: The script then gives the user the option to upload the created Docker image to DockerHub. In this instance, the user chooses not to upload it (option “1”).

4. Build Information: Following user input, the script provides important build information. This includes the build date, the directory where Docker is working (“Docker context”), the Dockerfile location, the resulting Docker image name (in this case, “svetekllc/artela:v0.4.2-beta-node”), the node type (“node”) and the version (“v0.4.2-beta”).

5. Building Process: The script proceeds to execute the Docker build process. It shows the steps it’s taking, such as loading .dockerignore files, loading build definitions from the Dockerfile, and loading metadata for various base images. The script provides progress updates and details on each step.

6. Build Completion: Once the Docker image building process is complete, the script indicates that the build has finished.

In summary, this script automates the creation of Docker images for specific blockchain node types and provides clear feedback to the user about the build’s progress and final outcome. It streamlines the process of creating and configuring Docker images for blockchain nodes, making it more efficient and user-friendly.

## Run docker-compose
Using docker-compose makes it easier to create a container by passing all the necessary parameters and variables to create it.

Rename the node.env.example file to node.env and fill in all the variables inside the file before create a docker container.

Run the command:
```bash
docker compose up -d
```

