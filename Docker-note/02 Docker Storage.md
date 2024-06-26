# Docker Storage

Learn to master directory mounting and data volumes to ensure container data is not lost. Containers themselves are like small virtual machines, making modifications inconvenient. Moreover, if a container is deleted, the stored data will also be lost.

## Force remove all currently running containers with the following command:

![Diagram 16](../images/Picture16.png)

## Print all container IDs:

![Diagram 17](../images/Picture17.png)

## Use directory mounting to solve data loss issues:

Add the `-v` statement to point the host machine address to the container's internal address. If the host directory does not exist, it will be automatically created. Even if the container is deleted, the external folder still exists. Restarting with the following command will show that the previously modified content remains unchanged.

![Diagram 18](../images/Picture18.png)

Conversely, modifying within the container and then accessing from outside will show consistent content. The following command demonstrates modifying the container internally and then exiting:

![Diagram 19](../images/Picture19.png)

Return to the host container and restart; the modifications will persist:

![Diagram 20](../images/Picture20.png)

## Volume mapping ensures that the host files are successfully mapped:

Once mapping is successful, the host files will contain all the files from the container image, consistent with the container content at the initial startup. Here, the volume name `ngconf` is configured:

![Diagram 21](../images/Picture21.png)
![Diagram 22](../images/Picture22.png)

Docker uniformly places configuration files in this location, accessible from the host machine:

![Diagram 23](../images/Picture23.png)

Entering this location reveals our volume `ngconf`. Inside `ngconf`, all configuration files are in a folder named `data`:

![Diagram 24](../images/Picture24.png)

Volumes can also be manually created and viewed with the following command. Even if the container is deleted, the volume will be retained. Restarting with the same volume will preserve previous modifications:

![Diagram 25](../images/Picture25.png)

