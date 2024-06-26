# Docker Commands

## Why Docker?

Docker is an open-source platform for developing, delivering, and running applications. It enables developers to package applications and all their dependencies into a standardized unit called a container, ensuring that applications run consistently in any environment. Here are some primary reasons for using Docker:

1. **Consistent Development and Production Environments:**
   Docker containers include applications and all their dependencies, ensuring consistent behavior across different environments (such as development, testing, and production). This helps reduce environment-related issues, improving application stability and reliability.

2. **Lightweight and Efficient Virtualization:**
   Docker containers are more lightweight compared to traditional virtual machines, as they do not require the overhead of a full operating system. This allows more instances to run on the same hardware, increasing resource utilization.

3. **Simplified Continuous Integration and Continuous Delivery (CI/CD):**
   Docker integrates well with CI/CD tools, making the build, test, and deployment processes more automated and efficient. Developers can quickly create and destroy test environments, accelerating the development and delivery cycle.

4. **Dependency Management:**
   Docker containers package applications and all their dependencies, eliminating the "works on my machine" problem. Developers no longer need to worry about dependency conflicts or missing libraries.

5. **Cross-Platform Compatibility:**
   Docker containers can run on any platform that supports Docker, including local machines, cloud servers, and data centers. Developers can easily migrate applications across different operating systems and hardware platforms.

6. **Modular and Microservices Architecture Support:**
   Docker containers simplify and enhance the implementation of microservices architecture. Each microservice can run in an independent container, facilitating independent development, testing, deployment, and scaling.

7. **Community Support and Ecosystem:**
   Docker has extensive community support and a rich ecosystem, including thousands of pre-built images on Docker Hub, various open-source tools, and enterprise-level solutions. These resources significantly simplify the use and management of containers.

## How Docker Works

![Diagram 1](./images/picture1.png)

## Understanding Containers

![Diagram 2](./images/picture2.png)

## Image Operations

![Diagram 3](./images/picture3.png)

## Container Operations

![Diagram 4](./images/picture4.png)

## Docker run Details:

Running in the background + custom naming
At this point, you will find that accessing nginx is not possible because it is only running within the current container and cannot be accessed from the external host. Port mapping is required, assuming you use `-p 88:80`, which maps the external port 88 directly to the internal port 80 of the container.

![Diagram 5](./images/picture5.png)
![Diagram 6](./images/picture6.png)

Note: Container ports can be reused, but host ports cannot be reused.
Each Docker container can be seen as an independent Linux system.

![Diagram 7](./images/picture7.png)

Reading the official Docker Hub documentation can provide more information about this official container, such as the location of the default web files.

![Diagram 8](./images/picture8.png)

Use `docker exec` to interact with a single container. After entering this container, use `ls` to check the current file directory, which is very similar to Linux. Here, the content of the default web file has been modified. You can use the `exit` command to exit the current container.

![Diagram 9](./images/picture9.png)

## Saving Images

![Diagram 10](./images/picture10.png)

## Sharing with the Community

After logging in, you can share images, each with its unique name, usually in the format `username/image-name`. You need to use `docker tag` to rename it. No matter how you rename it, the image ID remains unchanged.

![Diagram 11](./images/picture11.png)
![Diagram 12](./images/picture12.png)

Use `docker push` with the image tag to push.

![Diagram 13](./images/picture13.png)

You can set your latest image as `latest`, so when others download it without specifying a version number, it will not report an error and will default to downloading the latest version of the image.

![Diagram 14](./images/picture14.png)

## Summary

![Diagram 15](./images/picture15.png)
