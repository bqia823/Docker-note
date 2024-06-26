# Docker Network

Each Docker container has its own unique IP address, allowing containers to communicate with each other.

![Diagram 26](../images/Picture26.png)

## Docker Network

The `docker network` command encompasses all network-related commands.

![Diagram 27](../images/Picture27.png)

## Custom Network

Create a custom network.

![Diagram 28](../images/Picture28.png)

## Start Two Containers with a Custom Network

Use the custom network to start two containers.

![Diagram 29](../images/Picture29.png)

## Access Using Container Internal Network

Access using the internal network of the container.

![Diagram 30](../images/Picture30.png)

The page data is displayed normally after pressing Enter.

![Diagram 31](../images/Picture31.png)

## Best Practices Using MySQL as an Example

Best practices, using MySQL as an example.

![Diagram 32](../images/Picture32.png)

You can find more information in the official documentation. For example, files ending with `.cnf` will be considered MySQL configuration files by default.

![Diagram 33](../images/Picture33.png)

The documentation provides the location of MySQL data storage. There are details that may not be mentioned, such as the port. The default port for MySQL is 3306.

![Diagram 34](../images/Picture34.png)

You can find image version tags in the tag section. If no tag is specified, the latest version will be used by default.

![Diagram 35](../images/Picture35.png)

## Running a New Container Instance with `docker run`

The backslash `\` is used for line continuation. The `docker run` command is used to run a new container instance.

- The `-d` parameter runs the container in detached mode, meaning it will run in the background and not block the current terminal.
- The `-p 3306:3306` parameter maps port 3306 on the host to port 3306 in the container. This is MySQL's default port, allowing you to access MySQL services in the container through port 3306 on the host.
- The `-v /app/myconf:/etc/mysql/conf.d` parameter mounts a volume, mapping the host directory `/app/myconf` to the `/etc/mysql/conf.d` directory inside the container. This directory is typically used to store MySQL configuration files, so you can modify MySQL configuration files on the host and immediately apply them to the MySQL service inside the container.
- Another `-v /app/mydata:/var/lib/mysql` parameter maps the host directory `/app/mydata` to the `/var/lib/mysql` directory inside the container. This directory is where MySQL stores its data, allowing you to persist MySQL data on the host.
- The `-e MYSQL_ROOT_PASSWORD=123456` parameter sets an environment variable, configuring the MySQL root user password to `123456`.
- The `mysql:8.0.37-debian` specifies the Docker image and tag to use, indicating MySQL version 8.0.37 based on a Debian image. If the image is not available locally, Docker will automatically pull it from Docker Hub.

![Diagram 36](../images/Picture36.png)

