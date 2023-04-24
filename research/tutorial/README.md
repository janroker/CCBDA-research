# CCBDA-research

# Homework research project

One of the objectives of the **homework research project** is to study a little bit in-depth a subject that draws your attention and interest related to Cloud Computing and Big Data Analytics. It is a common practice in computer science where professionals regularly need to **increase their knowledge on new topics that they might need to use for their daily work**.

During the research, you need to be able _to find reliable and trustworthy sources of information_, understand them and try to invest as much or as little time as necessary to decide whether you are going to spend more time learning about the subject.

Another of the objectives of this homework assignment is to **cooperate and share your knowledge** with your peers and help each other to be able to have a broader understanding of Cloud Computing and Big Data Analytics. Therefore, to focus your research, I would like you to think about the information that you will be sharing from your classmates perspective _(use the following ideas to center your research focus not like the report index)_:

- What would you like to know about the presented topic to be able to decide if it is worth going in-depth or stop and take a different approach?
- What do people say regarding the subject you are studying: is it very successful? Is it mature enough? Do many people praise or criticize it?
- What has been your personal experience regarding the subject? What lessons have you learned?
- Share some relevant sources of information to learn more about the topic (URLs of websites, Articles, Blogs, PDF files, online courses, etc.)

A final objective of this assignment is to be able to **share the information attractively and concisely**. You can't expect your audience to invest lots of time on a topic that may not be of interest. Therefore I encourage you to deliver a short, meaningful, and attractive **tutorial**.

## Instructions to deliver the assigment

For **every team of 5 people**, **two of them** will be preparing a tutorial on a process. It can be something that they are using for their course project or that they are interested in digging a bit further.

To have more variety on the topics covered, _please contact your teacher before beginning preparing the tutorial_.

Groups of two people need to create a folder in their project repo named "research" and then a `"/research/tutorial/README.md"` file with the explanations, images, pieces of code, etc. similar to the ones used for your laboratory sessions.

The **remaining** team members will be assigned the two tutorials elaborated by the other teams. They will need to follow the tutorial and submit evidence of their job in `"/research/response1/README.md"` and `"/research/response2/README.md"` including **feedback for the authors** and **their grade** on how well elaborated and interesting they find it.

Since each team will only be able to experiment with two assigments the day of the presentation each team will be explaining their topic to the whole class.

Add a file `"/research/authors.json"`

```json5
{
  creators: ["NAME1@est.fib.upc.edu", "NAME2@est.fib.upc.edu"],
  validators: ["NAME3@est.fib.upc.edu", "NAME4@est.fib.upc.edu"],
}
```

The teacher will evaluate the tutorials based on the documentation, presentation and the feedback offered by the groups of 2 students evaluating.
Once all tutorials evaluated, they will be included in this repository to make them available for everyone.

**Grade**:

- tutorial documentation
- presentation _(use a PDF that can be attached in the repo)_ and explanations
- feedback offered by the two teams following the tutorial

## Tutorials and assignment

| Team | Presentation | Assignment 1 | Assignment 2 |
| :--- | :----------: | :----------: | :----------: |

NOTE: please update the file `"/research/authors.json"` as stated above.

## Deadlines

- For the tutorial documentation presentation May 8th 2023
- In Class presentation of each topic May 16th 2023
- For the tutorial evaluation and feedback May 22th 2023

---

The initial idea is to containerise the application and deploy it on a local Kind cluster. This could include:

1. How to containerise the application
2. What is Kubernetes
3. What is Kind
4. How to deploy Kind
5. How to deploy application on Kind cluster
6. If there is time, we could also try to expand the tutorial with how to do the same with AWS EKS

For reference, we would use YouTube tutorials:

- Kind [tutorial](https://www.youtube.com/watch?v=m-IlbCgSzkc&t=525s&ab_channel=ThatDevOpsGuy) from That DevOps Guy
- Docker development [tutorial](https://www.youtube.com/watch?v=wyjNpxLRmLg&list=PLHq1uqvAteVvqQaaIAvfIWWTL_JmmXcfg&ab_channel=ThatDevOpsGuy) from That DevOps Guy
- Official Kubernetes, Kind, Docker documentations
- Tutorials and official documentation on how to use AWS EKS
- Some additional resources

## Docker

https://docker-curriculum.com/

Docker is a platform for developing, shipping, and running applications in containers. Containers are lightweight, portable, and self-contained environments that can run an application and all its dependencies, allowing developers to package their applications into a single container that can be deployed to any environment.

Docker allows developers to create, manage, and deploy containers easily, regardless of the underlying infrastructure. It abstracts away the complexity of infrastructure management and provides a consistent environment for developers and operations teams, enabling faster and more reliable application delivery.

Docker has become a popular tool in DevOps and cloud computing, as it allows developers to build and test applications in a containerized environment, and deploy them to any cloud platform or on-premise infrastructure with ease. It also enables organizations to scale their applications more efficiently, as containers can be easily replicated and deployed across multiple environments.

Containerization is the process of packaging an application and its dependencies into a single, self-contained unit called a container. Containers provide a way to isolate and run applications with all their dependencies in a consistent and predictable environment.

In the context of Docker, containerization involves using Docker containers to package an application and all its dependencies into a single container image. A Docker container image is a lightweight, portable, and self-sufficient package that contains everything needed to run an application, including the code, runtime, system tools, libraries, and settings.

Docker containers are based on the concept of operating system virtualization, which allows multiple containers to run on the same host operating system while remaining isolated from each other. Each Docker container runs as a separate process, with its own file system, network interface, and resources, such as CPU and memory.

The benefits of containerization with Docker include:

Portability: Docker containers can be run on any platform that supports Docker, making it easy to move applications between environments.
Consistency: Docker containers provide a consistent environment for applications to run, regardless of the underlying infrastructure.
Efficiency: Docker containers are lightweight and require minimal resources, allowing for efficient use of infrastructure.
Scalability: Docker containers can be easily replicated and deployed across multiple environments, enabling organizations to scale their applications more efficiently.
Overall, containerization with Docker provides a more efficient and reliable way to develop, deploy, and manage applications.

Yes, Docker is still very commonly used today, and its usage continues to grow. Docker has become a popular tool in DevOps and cloud computing, and it is widely used by organizations of all sizes and across a range of industries.

Docker is commonly used in cloud-native applications, microservices architectures, and container orchestration platforms like Kubernetes. It is also used in DevOps workflows, where developers use Docker containers to build, test, and deploy applications in a consistent and repeatable way.

Some of the popular use cases for Docker include:

Application development and testing: Docker containers provide a lightweight and portable way to package and test applications, enabling developers to quickly iterate and deploy their code.
Cloud computing and serverless computing: Docker containers can be used to run applications in cloud platforms like Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP), as well as in serverless computing environments like AWS Lambda and Google Cloud Functions.
Continuous integration and continuous delivery (CI/CD): Docker containers can be used in CI/CD workflows to automate the build, test, and deployment of applications, enabling faster and more reliable software delivery.
Microservices architectures: Docker containers are often used in microservices architectures, where applications are broken down into smaller, independent services that can be deployed and scaled independently.
Overall, Docker is widely used today, and its popularity is expected to continue to grow as more organizations adopt cloud-native architectures and DevOps practices.

## Kubernetes

Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications. Kubernetes was originally developed by Google, and it has since become one of the most popular tools in cloud computing and DevOps.

Kubernetes is often used in conjunction with Docker, as Docker provides the containerization technology that Kubernetes uses to run applications. Kubernetes can also work with other containerization tools like containerd, CRI-O, and rkt.

Kubernetes is commonly used in cloud-native applications and microservices architectures, as it provides a way to manage and scale complex containerized applications. It is widely used in cloud platforms like AWS, Microsoft Azure, and Google Cloud Platform, as well as in on-premise data centers.

Some of the benefits of using Kubernetes include:

Scalability: Kubernetes enables organizations to scale their applications up or down based on demand, making it easy to handle traffic spikes and other fluctuations.
Resilience: Kubernetes provides features like self-healing and automatic failover, ensuring that applications remain available even in the face of hardware or software failures.
Portability: Kubernetes provides a consistent way to deploy and manage applications across different environments, making it easy to move applications between cloud platforms and on-premise infrastructure.
Automation: Kubernetes automates many of the tasks involved in managing containerized applications, reducing the need for manual intervention and minimizing the risk of human error.
However, there are also some challenges associated with using Kubernetes. Some of the potential drawbacks include:

Complexity: Kubernetes can be complex to set up and manage, especially for organizations that are new to containerization and cloud computing.
Learning curve: Kubernetes has a steep learning curve, and it can take time for developers and operations teams to become proficient in its use.
Resource requirements: Kubernetes requires significant resources to run, both in terms of hardware and personnel. Organizations need to have dedicated teams and infrastructure in place to manage and maintain Kubernetes clusters.
Overall, Kubernetes is a powerful tool for managing containerized applications, and it is widely used in cloud computing and DevOps. However, organizations need to carefully consider the benefits and drawbacks of using Kubernetes before adopting it in their workflows.

When managing Kubernetes infrastructure and developing apps for deployment on Kubernetes, there are several common rules and best practices that can help ensure the reliability, security, and efficiency of the system. Some of these include:

Use version control: Store your Kubernetes configuration files and application code in version control to enable reproducible builds and deployments.

Follow the principle of least privilege: Limit access to Kubernetes resources by assigning appropriate roles and permissions to users and service accounts.

Use namespaces: Use namespaces to isolate workloads and prevent conflicts between applications and services.

Use labels and annotations: Use labels and annotations to identify and categorize Kubernetes objects, making it easier to manage and troubleshoot them.

Use container images from trusted sources: Use container images from trusted sources, and regularly update them to ensure that they are free from vulnerabilities.

Use resource limits: Use resource limits to prevent individual containers from consuming excessive CPU and memory resources, which can affect the performance of other containers on the same node.

Use liveness and readiness probes: Use liveness and readiness probes to ensure that containers are running correctly and are ready to receive traffic.

Use rolling updates: Use rolling updates to deploy new versions of applications with minimal downtime and disruption to users.

Monitor and log Kubernetes objects: Monitor and log Kubernetes objects to detect and troubleshoot issues, and to identify opportunities for optimization.

Regularly audit and review your system: Regularly audit and review your Kubernetes infrastructure and applications to identify security vulnerabilities, performance issues, and other areas for improvement.

Overall, following these rules and best practices can help ensure the stability and reliability of your Kubernetes infrastructure and applications, and help you to better manage and troubleshoot issues when they arise.

## Kind (Kubernetes in Docker)

Kind (Kubernetes in Docker) is a tool for running local Kubernetes clusters using Docker container nodes. It allows users to easily create, manage, and test Kubernetes clusters on their local machines or in CI/CD pipelines.

A Kind cluster runs on a user's machine and can be used for a variety of purposes, such as:

Development and testing: Developers can use Kind to create a local Kubernetes environment to test and iterate on applications before deploying them to a production cluster.

Continuous integration and deployment: CI/CD pipelines can use Kind to run integration tests against a Kubernetes cluster to verify that the application works correctly before deploying it to production.

Education and training: Kind can be used to create a local Kubernetes environment for educational and training purposes, allowing users to learn and experiment with Kubernetes without the need for cloud infrastructure.

Kind provides a lightweight and portable way to create Kubernetes clusters, making it easier for developers to experiment with and test their applications locally. It can also be used in conjunction with other tools, such as kubectl and Helm, to streamline the development and deployment process.

## Containerizing an application

Containerizing an application typically involves the following steps:

Choose a containerization technology: There are several containerization technologies available, such as Docker, Podman, and LXD. Choose the one that best fits your needs.

Create a Dockerfile: A Dockerfile is a text file that contains a set of instructions for building a Docker image. It specifies the base image, dependencies, and other configurations needed to run the application inside a container.

Build the Docker image: Use the Dockerfile to build a Docker image by running the "docker build" command. This command will create a new image based on the instructions in the Dockerfile.

Run the Docker container: Once the Docker image is built, use the "docker run" command to start a container based on the image. You can specify various options such as environment variables, port mappings, and volume mounts.

Test the containerized application: Verify that the application is working correctly by testing it inside the container.

Push the Docker image to a registry: If you plan to deploy the containerized application to a production environment, you may want to push the Docker image to a container registry like Docker Hub or Amazon ECR.

Deploy the containerized application: Finally, deploy the containerized application to your production environment by running the container on a host or using a container orchestration platform like Kubernetes.

Overall, containerizing an application involves creating a Docker image that contains all the necessary dependencies and configurations to run the application inside a container, and then running the container in a production environment.

# How to run Kind


# How to deploy application on Kind cluster

# How to do deploy an application to AWS EKS

