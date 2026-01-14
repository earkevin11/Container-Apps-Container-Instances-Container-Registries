# Container-Apps-Container-Instances-Container-Registries

# What are containers?
- To understand what container security is, you must know what exactly a container is.

Container image → the blueprint (what the app looks like)

Container → a running instance of that image

Container platform → the system that runs and manages containers

- Container is a package of software and its dependencies.
- Example: Think of a software container like a shipping container
- The container holds everything for the item inside
- - The application itself
  - Runtime (e.f., .NET, Node.js)
  - Libraries and dependencies
  - Config files
- The container runs the same way everywhere
- - on a developer's laptop
    In test environments
    in production (cloud or on-prem)

Software container is like a shipping container
- It doesn't care what truck or ship it's on (Linux VM, cloud service, kubernetes).
- It GUARANTEES the contents arrive unchanged and predictable.

<img width="1025" height="577" alt="image" src="https://github.com/user-attachments/assets/f270edaf-745d-4766-a169-eb16271201c8" />

In above image, you have the Docker engine, which acts as an interface between the containerized application and the host operating system. It allocates the operating system resources to the containers and ensures that the containers are isolated from one another. 

# What do organizations use Container? 
1. Consistency
- It provides consistency and solves the issue of "Well, it works on my machine"
  
2. Faster deployments
- Container start in seconds
- Easy to deploy, roll back, and scale

3. Better resource efficiency
- Much lighter than full virtual machines
- Containers share the host OS kernel

4. Scalability
- Easy to run multiple copies of an app when demand increases
- Works well with orchestrator like Kubernetes

5. Isolation and Security
- Each app runs in its own isolated environment
- Reduces blast radius compared to shared runtimes

Common Container platforms
- Docker
- Kubernetes
- Azure Kubernetes Service
- Azure Container Apps
- Azure Container Instances


# What are Azure Container Apps?

Azure Container Apps (ACA)

What it is: A managed container platform built on Kubernetes (you don’t see K8s directly)

Important: ACA is self healing = the platform automatically keeps your apps running when something goes wrong. Azure Container Instances are not self-healing.

- Under the hood, Azure Container Apops is built on Kubernetes, which is why it has orchestration. It inherits orchestration features. Azure Container instances is NOT built on kubernetes.


Supports:
1. Autoscaling
2. Revisions
3. Traffic splitting
4. Ingress

Think of it like: “I want Kubernetes-like features without managing Kubernetes.”

Common use cases:
1. Microservices
2. APIs
3. Event-driven workloads
4 .Modern app platforms



# What are Azure Container Instances?

- What it is: A service that runs SINGLE containers or small container groups
- No orchestration = no auto-recovery
- No infrastructure to manage as Microsoft manages it.

Important: ACI is NOT self-healing.

ACI behavior:

- You say: “Run this container with these settings”
- Azure starts it
- That’s it

If something goes wrong:
1. Container crashes ❌ → it stays down
2. Traffic spikes ❌ → no automatic scale
3. Need 3 copies ❌ → you must create them manually
4. Want rolling deploy ❌ → you must script it


Think of it like: “Run this container now, and I don’t want to manage servers.”
- Common use cases:
1. Short-lived jobs
2. Scripts
3. Simple APIs
4. Burst workloads

Side by Side comparison below:

<img width="1182" height="688" alt="image" src="https://github.com/user-attachments/assets/5518a8fe-36d2-484a-a61f-7a54bf4c4063" />

# What does Azure Container Registry have to do with ACAs and ACIs?

- Azure Container Registry (ACR) is a private warehouse for container images.
- If containers are running apps, and images are the blueprints, then:
- ACR = the secure place where your blueprints are stored and versioned

Analogy: 

Why is a registry necessary?
1. A container platform cnnot run an app unless it can pull from an image from somehwere. That "somewhere" must:
- Store images
- Version them
- Allow secure access
- Be highly available

Why do organizations use Azure Container Registry?
1. Security!!!!!!!!
- Private secure repository of images. It stores and versions container images so Azure container platforms can reliably and securely deploy applciations.
- Integrated with Entra ID


