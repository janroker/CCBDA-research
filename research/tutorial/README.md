# Homework research project

In this tutorial we are going to leverage Docker to show how Docker and Docker containers can be used when developing, testing, managing and deploying applications. We will also use simple examples to show how we can use Kubernetes to deploy and manage our applications.

Lets begin by defining the tools that we are going to use.

## Docker

### What is Docker?

Docker is a platform for developing, shipping, and running applications in containers. It allows developers to **create, manage, and deploy containers** easily, regardless of the underlying infrastructure.

Docker has become a popular tool in DevOps and cloud computing, as it allows developers to build and test applications in a containerized environment, and deploy them to any cloud platform or on-premise infrastructure with ease. It also enables organizations to scale their applications more efficiently, as containers can be easily replicated and deployed across multiple environments.

### Containers

Containers are **lightweight**, **portable**, and **self-contained environments** that can run an application and all its dependencies, allowing developers to package their applications into a single container that can be deployed to any environment. Containers provide a way to isolate and run applications with all their dependencies in a consistent and predictable environment.

#### Containerization

Containerization is the process of packaging an **application and its dependencies** into a single, **self-contained** unit called a container.

By packaging the applications into containers:

- Applications can be abstracted from the environment in which they actually run
- Application's environment and host's environment are **decoupled**
- A **predictable environment**, that is **isolated** from the rest of the applications and can be run anywhere, is created

In the context of Docker, containerization involves using Docker containers to package an application and all its dependencies into a single **container image**. A Docker container image is a lightweight, portable, and self-sufficient package that contains everything needed to run an application, including the **code, runtime, system tools, libraries, and settings**.

#### Image vs container

To clarify, Docker **images and containers are different things**. Both containers and images allow users to specify application dependencies and configurations and to describe everything necessary for a machine to run that application. However, containers and images have different lifecycles:

- **Docker image** - read-only template containing instructions for creating a container
- **Docker container** - instance of a docker image, running on a completely isolated environment

#### What are the benefits?

Docker containers are based on the concept of operating system virtualization, which allows multiple containers to run on the same host operating system while remaining isolated from each other. Each Docker container runs as a **separate process**, with its own **file system, network interface, and resources, such as CPU and memory**.

The benefits of containerization with Docker include:

- **Portability**: Docker containers can be run on any platform that supports Docker, making it easy to move applications between environments.
- **Consistency**: Docker containers provide a consistent environment for applications to run, regardless of the underlying infrastructure.
- **Efficiency**: Docker containers are lightweight and require minimal resources, allowing for efficient use of infrastructure.
- **Scalability**: Docker containers can be easily replicated and deployed across multiple environments, enabling organizations to scale their applications more efficiently.

### Where is it used?

Overall, containerization with Docker provides a more efficient and reliable way to develop, deploy, and manage applications.

Docker is commonly used in cloud-native applications, microservices architectures, and container orchestration platforms like Kubernetes. It is also used in DevOps workflows, where developers use Docker containers to build, test, and deploy applications in a consistent and repeatable way.

Due to these benefits, containers (& Docker) have seen widespread adoption. Companies like Google, Facebook, Netflix and Salesforce leverage containers to make large engineering teams more productive and to improve utilization of compute resources.

### docker-compose

Docker Compose is a tool that allows you to define and run **multi-container Docker applications** (containerized applications that are made of multiple containers). It is used to define the **services** that make up your application and how they interact with each other. With Docker Compose, you can configure, start, and stop multiple Docker containers with a **single command**.

The main purpose of Docker Compose is to simplify the process of managing multi-container Docker applications. With Docker Compose, you can define your application as a **set of services**, each running in its own container, and **configure how these services interact** with each other.

A **Docker Compose file** is a YAML file that defines the configuration of the services that make up your application. It includes information such as the **image** to use for each service, the **ports to expose**, and the **environment variables** to set. You can also define **network connections between containers**, **mount volumes for persistent data**, and set up **dependencies between services**.

Docker Compose is particularly useful for developing and testing complex applications, as it allows you to define and run the entire application stack on your local machine. This makes it easier to test changes and debug issues in a local environment that closely mirrors the production environment.

## Kubernetes

### What is Kubernetes?

Kubernetes is an open-source **container orchestration platform** that automates the deployment, scaling, and management of containerized applications. Kubernetes was originally developed by Google, and it has since become one of the most popular tools in cloud computing and DevOps.

Kubernetes is often used in conjunction with Docker, as **Docker provides the containerization technology that Kubernetes uses to run applications**. Kubernetes can also work with other containerization tools like containerd, CRI-O, and rkt.

Kubernetes is commonly used in cloud-native applications and microservices architectures, as it provides a way to manage and scale complex containerized applications. It is widely used in cloud platforms like AWS, Microsoft Azure, and Google Cloud Platform, as well as in on-premise data centers.

### Benefits

Some of the benefits of using Kubernetes include:

- **Scalability**: Kubernetes enables organizations to scale their applications up or down based on demand, making it easy to handle traffic spikes and other fluctuations.
- **Resilience**: Kubernetes provides features like self-healing and automatic failover, ensuring that applications remain available even in the face of hardware or software failures.
- **Portability**: Kubernetes provides a consistent way to deploy and manage applications across different environments, making it easy to move applications between cloud platforms and on-premise infrastructure.
- **Automation**: Kubernetes automates many of the tasks involved in managing containerized applications, reducing the need for manual intervention and minimizing the risk of human error.

### Challenges

Some of the potential drawbacks include:

- **Complexity**: Kubernetes can be complex to set up and manage, especially for organizations that are new to containerization and cloud computing.
- **Learning curve**: Kubernetes has a steep learning curve, and it can take time for developers and operations teams to become proficient in its use.
- **Resource requirements**: Kubernetes requires significant resources to run, both in terms of hardware and personnel. Organizations need to have dedicated teams and infrastructure in place to manage and maintain Kubernetes clusters.

Overall, Kubernetes is a powerful tool for managing containerized applications, and it is widely used in cloud computing and DevOps. However, organizations need to carefully consider the benefits and drawbacks of using Kubernetes before adopting it in their workflows.

## Kind (Kubernetes in Docker)

Kind (Kubernetes in Docker) is a tool for running _local Kubernetes clusters using Docker container nodes_. It allows users to **easily create, manage, and test Kubernetes clusters on their local machines** or in CI/CD pipelines.

A Kind cluster runs on a user's machine and can be used for a variety of purposes, such as:

- Development and testing: Developers can use Kind to create a local Kubernetes environment to test and iterate on applications before deploying them to a production cluster.
- Continuous integration and deployment: CI/CD pipelines can use Kind to run integration tests against a Kubernetes cluster to verify that the application works correctly before deploying it to production.
- Education and training: Kind can be used to create a local Kubernetes environment for educational and training purposes, allowing users to learn and experiment with Kubernetes without the need for cloud infrastructure.

Kind provides a **lightweight and portable** way to create Kubernetes clusters, making it **easier for developers to experiment** with and test their applications **locally**. It can also be used in conjunction with other tools, such as kubectl and Helm, to streamline the development and deployment process.

## Prerequisites

The `getting started guide on Docker` has detailed instructions for setting up Docker on [Mac](https://docs.docker.com/desktop/install/mac-install/), [Linux](https://docs.docker.com/engine/install/ubuntu/) and [Windows](https://docs.docker.com/desktop/install/windows-install/).

Once you are done installing Docker, test your Docker installation by running the following:

```bash
$ docker run hello-world

Hello from Docker.
This message shows that your installation appears to be working correctly.
...
```

Confirm that the docker-compose was installed alongside the Docker Engine by running the following:

```bash
$ docker compose version
Docker Compose version vN.N.N
```

If you had followed the `getting started guide on Docker` and installed the [Docker Desktop](https://www.docker.com/products/docker-desktop/), then the previous command should work. However, if you had only installed [Docker Engine](https://docs.docker.com/engine/) and the previous command did not work, then follow [this](https://docs.docker.com/compose/install/linux/#install-using-the-repository) guide to install docker-compose too.

## Using Docker for application development

As we have already mentioned, Docker container image contains an application and all that is needed to run that application in a single package. A Docker container image is lightweight, portable and self-suficient.

In this section we will leverage container's self-suficiency to show why it can be a very powerfull tool in application development.

### Problem

Application development process requires tools and environments that are able to build a runnable, debug an application and run it. For example, to develop and run a Java application you need JDK installed at least. This implies having a **right version** of JDK installed, having all the **environment** variables **correctly set-up** so that you can execute java commands, etc.

What happens when you need multiple versions of environments to manage because you are maintaining multiple different applications at the same time? (I know, Java is not the best example here because it is hugely backwards compatible. There a lot of different tools that are not backwards compatible and you can't use same tooling to develop different applications.)

### Solution - packaging application, settings, and tools in a single package

There are multiple benefits to this: 

- **Saves time** - there is no configuration needed, you just run the container and you are good to develop.
- **Environment setup is automated** - all you need to do is build the image and run the container, tools and enviroment are configured automatically. There is no need to explicitly install Vx.y.z of some specific tool and configure everything so that everything works as expected.
- **Host machine is less cluttered** - there is no need to install tools (different versions) on the host - isolation and decoupling goes both ways.
- **Cleanup is easier** - all you need to do to cleanup is run the `docker rm` command; there is no searching the file-system in pursuit of forgotten tools that are no longer neccessary.

Of course, there are downsides to this such as:

- Developers need to be familiar with Docker
- There is additional configuration needed to set an initial development process
- Development tools (IDEs) have to be able to make use of containers while developing

## Task 1 - developing with Docker

In this task we will use the [Visual Studio Code](https://code.visualstudio.com/) and the source code provided in the `research/tutorial/task1` folder. If you are completely unfimilliar with Docker, you can follow [Hello World](https://docker-curriculum.com/#hello-world) and [Webapps with Docker](https://docker-curriculum.com/#webapps-with-docker) sections of the `docker-curriculum guide` to get to know a few basic commands that are frequently used.

### Task 1.1 Docker volumes and interactive terminal

According to the [documentation](https://docs.docker.com/storage/volumes/), volumes are used for persisting data:

`Volumes are the preferred mechanism for persisting data generated by and used by Docker containers. While bind mounts are dependent on the directory structure and OS of the host machine, volumes are completely managed by Docker.`

Here we will use the [bind mount](https://docs.docker.com/storage/bind-mounts/) volume type. It is a volume type where **the file or directory is referenced by its absolute path on the host machine**.

To see Docker volumes in action, we open a terminal window, position ourselves in the project's directory (working directory should be this repository's root) and execute the following command:

```bash
docker run --rm -it -v .:/work -w /work alpine:3.9 /bin/sh
```

This command can be read as:

```bash
docker run --rm -it -v hostPath:containerPath -w /work alpine:latest /bin/sh
```

It will download and run the alpine image directly in one go using docker run. The --rm flag automatically removes the container when it exits and the -it flag specifies an interactive terminal which makes it easier to kill the container with Ctrl+C.

The `-v hostPath:containerPath` option specifies that a bind mount Docker volume shall be used. The `hostPath` specifies the path on the host that will be mapped (visible) inside the container at the `containerPath`, relative to the root of the container's file-system.

When we had executed that command, a container was run and containers working directory was set to be `/work`, as specified by the `-w` option.

Finally, the path of the `alpine:Vx.y.z` behind a `:` symbol specifies a version of the alpine image to be used and `/bin/sh` specifies the **ENTRYPOINT** for the container.  The ENTRYPOINT instruction is used to configure the executables that will always run after the container is initiated. In this case it is a `bash shell`.

```bash
(base) [janroker@janroker research]$ docker run --rm -it -v .:/work -w /work alpine:3.9 /bin/sh
Unable to find image 'alpine:3.9' locally
3.9: Pulling from library/alpine
31603596830f: Pull complete 
Digest: sha256:414e0518bb9228d35e4cd5165567fb91d26c6a214e9c95899e1e056fcd349011
Status: Downloaded newer image for alpine:3.9
```

After the command finishes, we can `execute commands inside the container interactively`. Each command that we execute reflects to the container's file-system and uses container's environment and binaries that are available in the container. For example, if we execute `ls /' command, we will se a listing of the container's root directory and not the root directory on the host.

```bash
/work # ls /
bin    dev    etc    home   lib    media  mnt    opt    proc   root   run    sbin   srv    sys    tmp    usr    var    work
```

We can now execute `ls .` command and we will see the same directory structure that is present in this repository's root. That is because we mapped the repository's root folder on the host to the `/work` in the container and then changed the working directory of the container to be the `/work` directory. Everything that we change in this folder is reflected on the host's file-system. That is what the `bind mount` does.

```bash
/work # ls
authors.json  response1     response2     tutorial

/work # pwd
/work
```

For example, we can now execute `echo "Hello!" > echo.txt` command and observe that a new file is visible on both the host and the container and that it contains "Hello!" message.

```bash
/work # echo "Hello!" > echo.txt

/work # ls
authors.json  echo.txt      response1     response2     tutorial

/work # cat echo.txt
Hello!

/work # 
```

![repository structure](images/task1_1.png)

There are many different ways to leverage this mechanism. For example, inside the container, with `apk add`, you could install some additional software that can only be executed on linux and use it to process files on a Windows host. We will now use that mechanism to develop applications inside a container and the changes that we make will be reflected on the host machine.

You can execute `exit` command and exit the container.

if we now run the `docker ps` command on the host machine, we will see that there are no containers running.

### Task 1.2 - Modify the code

We will now download a [web application](https://github.com/CCBDA-UPC/Assignments-2023/blob/master/Lab05.md#task-51-download-the-code-for-the-web-app) that we have already used in Lab5. Go ahead and follow the instructions given on the linked page to download a zip file that contains the application code.

Unzip the project at the following path - `/research/tutorial/task1/eb-signup`

That folder should now look like this:

![eb-signup folder](./images/task1_2.png)

#### Changes

Before containerizing the application, we will modify the code because we want to be able to test the application without having to create a new dynamodb table on the AWS academy

- Create `eb-signup/form/resources.py` with the following code:

```python
import boto3
import os
import logging

EB_SIGNUP_ENVIRONMENT = os.environ['EB_SIGNUP_ENVIRONMENT']
DYNAMO_ENDPOINT_URL = os.environ['DYNAMO_ENDPOINT_URL']
AWS_REGION = os.environ['AWS_REGION']
AWS_ACCESS_KEY_ID = os.environ['AWS_ACCESS_KEY_ID']
AWS_SECRET_ACCESS_KEY = os.environ['AWS_SECRET_ACCESS_KEY']
AWS_SESSION_TOKEN = os.environ['AWS_SESSION_TOKEN']

logger = logging.getLogger(__name__)

def get_dynamoDB_table(table):

    if EB_SIGNUP_ENVIRONMENT == 'dev':
        dynamodb = boto3.resource('dynamodb',
                            region_name=AWS_REGION,
                            endpoint_url=DYNAMO_ENDPOINT_URL)
        
        
        tables = list(dynamodb.tables.all())
        print(tables)
    else:
        dynamodb = boto3.resource('dynamodb',
                            region_name=AWS_REGION,
                            aws_access_key_id=AWS_ACCESS_KEY_ID,
                            aws_secret_access_key=AWS_SECRET_ACCESS_KEY,
                            aws_session_token=AWS_SESSION_TOKEN )
    return dynamodb.Table(table)

```

Here we have created a new function that will use `boto3` to obtain an AWS resource depending on the current application environment (development, testing, production...). This is because we will use local DynamoDB instance while developing and DynamoDB that is deployed on AWS in production.

Notice that we are using two new environment variables: `EB_SIGNUP_ENVIRONMENT` and `DYNAMO_ENDPOINT_URL`. We need the first one to know what is the current application environment and the second one so that we can specify that the DynamoDB instance is running locally.

- Modify the `eb-signup/form/models.py` with the following code:

```python
from django.db import models
import os
import logging
from .resources import get_dynamoDB_table

STARTUP_SIGNUP_TABLE = os.environ['STARTUP_SIGNUP_TABLE']

logger = logging.getLogger(__name__)


class Leads(models.Model):

    def insert_lead(self, name, email, previewAccess):
        try:
            table = get_dynamoDB_table(STARTUP_SIGNUP_TABLE)
        except Exception as e:
            logger.error(
                'Error connecting to database table: ' + (e.fmt if hasattr(e, 'fmt') else '') + ','.join(e.args))
            return 403
        try:
            response = table.put_item(
                Item={
                    'name': name,
                    'email': email,
                    'preview': previewAccess,
                },
                ReturnValues='ALL_OLD',
            )
        except Exception as e:
            logger.error(
                'Error adding item to database: ' + (e.fmt if hasattr(e, 'fmt') else '') + ','.join(e.args))
            return 403
        status = response['ResponseMetadata']['HTTPStatusCode']
        if status == 200:
            if 'Attributes' in response:
                logger.error('Existing item updated to database.')
                return 409
            logger.error('New item added to database.')
        else:
            logger.error('Unknown error inserting item to database.')

        return status

```

All we changed here is replaced a call to boto3 to obtain a 'dynamodb' resource with a call to our new `get_dynamoDB_table(STARTUP_SIGNUP_TABLE)` function.

#### Test the application

First, we need to get our local DynamoDB instance up and running. For this, we will use a DynamoDB Docker [image](https://hub.docker.com/r/amazon/dynamodb-local/). You can find more info on the provided link.

Open a terminal and execute the following command that will start our local DynamoDB instance:

```bash
docker run --rm -p 8001:8000 amazon/dynamodb-local -jar DynamoDBLocal.jar -sharedDb
```

Open a new terminal and use a AWS CLI to create a `gsg-signup-table`:

```bash
aws dynamodb create-table --endpoint-url http://localhost:8001 --region "us-east-1" \
    --table-name gsg-signup-table \
    --attribute-definitions \
        AttributeName=email,AttributeType=S \
    --key-schema \
        AttributeName=email,KeyType=HASH \
    --provisioned-throughput \
        ReadCapacityUnits=5,WriteCapacityUnits=5 \
    --table-class STANDARD
```

We are now ready to start our application. As we already know, our application is dependent on a few environment variables which we will set with the following commands before executing a command that will get our application up and running:

```bash
export DEBUG=True
export STARTUP_SIGNUP_TABLE=gsg-signup-table
export AWS_REGION=us-east-1
export AWS_ACCESS_KEY_ID=random
export AWS_SECRET_ACCESS_KEY=random
export AWS_SESSION_TOKEN=random
export EB_SIGNUP_ENVIRONMENT=dev
export DYNAMO_ENDPOINT_URL=http://localhost:8001

python manage.py runserver
```

Please visit the http://localhost:8000 and Sign up a few times.

When executing the following command, we should be able to see our new DynamoDB entries in the gsg-signup-table:

```bash
aws dynamodb scan --table-name gsg-signup-table --endpoint-url http://localhost:8001 --region "us-east-1" 
```

## Task 1.3 Containerizing the application

Containerizing an application typically involves the following steps:

- Choose a containerization technology: There are several containerization technologies available, such as Docker, Podman, and LXD. Choose the one that best fits your needs.
- **Create a Dockerfile**: A **Dockerfile** is a text file that contains a **set of instructions for building a Docker image**. It specifies the base image, dependencies, and other configurations needed to run the application inside a container.
- **Build the Docker image**: Use the Dockerfile to build a Docker image by running the `docker build` command. This command will create a new image based on the instructions in the Dockerfile.
- **Run the Docker container**: Once the Docker image is built, use the `docker run` command to start a container based on the image. You can specify various options such as environment variables, port mappings, and volume mounts.
- **Test the containerized application**: Verify that the application is working correctly by testing it inside the container.
- Push the Docker image to a registry: If you plan to deploy the containerized application to a production environment, you may want to push the Docker image to a container registry like Docker Hub or Amazon ECR.
- Deploy the containerized application: Finally, deploy the containerized application to your production environment by running the container on a host or using a container orchestration platform like Kubernetes.

Overall, containerizing an application involves creating a Docker image that contains all the necessary dependencies and configurations to run the application inside a container, and then running the container in a production environment.

---

Go ahead and create a text file in the root of the project - `/research/tutorial/task1/eb-signup/Dockerfile`

The file should look like this:

```Dockerfile
# Set the base image to use for any subsequent instructions that follow 
# and also give this build stage a name. The name is arbitrary
FROM python:3.11-slim-bullseye AS build_stage

# Create a "/app" directory inside the container
RUN mkdir /app/
WORKDIR /app/

# Copy project source from project root "." to working directory "/app" inside the container
COPY . /app/

# Install the dependencies
RUN pip install -r requirements.txt

# Start the server; Here we specify that the server must listen on all 
# interfaces because we will be accessing it from "outside the container"
CMD python manage.py runserver 0.0.0.0:8000
```

We are now ready to build our Docker image. This command will build a new docker image with a `eb-signup:1.0` tag and it will search for the Dockerfile in the current directory (note the "." at the end):

```bash
docker build -t eb-signup:1.0 .
```

Create .env file in the project root with the following content. We will use this file to set the environment variables when starting the container.

```.env
DEBUG=True
STARTUP_SIGNUP_TABLE=gsg-signup-table
AWS_REGION=us-east-1
AWS_ACCESS_KEY_ID=random
AWS_SECRET_ACCESS_KEY=random
AWS_SESSION_TOKEN=random
EB_SIGNUP_ENVIRONMENT=dev
DYNAMO_ENDPOINT_URL=http://localhost:8001
```

We will start our application inside the Docker container with the following command:

```bash
docker run --rm -p 8000:8000 --env-file .env --network="host" eb-signup:1.0
```

Please note the options that we have used:

- `-p` maps containers port 8000 to the port 8000 on the host -> format is `host_port:container_port`. We are using this option to expose the server to the host.
- `--env-file .env` specifies that the container environment should be set from the .env file.
- `--network="host"` is another very important option. Since our server is trying to communicate with another container which is our local DynamoDB, we need to set its network to "host" so that `localhost` is the same thing on the host machine and inside the Docker container. Notice the local DynamoDB endpoint url: `DYNAMO_ENDPOINT_URL=http://localhost:8001`. If we did not set the network option to "host", `localhost` would mean as if the container is contacting himself.

## Task 1.4 - simplifying things by using the docker-compose

## How to run Kind

## How to deploy application on Kind cluster

## How to do deploy an application to AWS EKS

https://github.com/marcel-dempers/docker-development-youtube-series