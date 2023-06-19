# AFFiNE Docker

The official Docker deployment solution for AFFiNE.

##  Install & Usage

Install AFFiNE with Docker
This guide assumes you already have an environment setup running docker.

Currently there are two main versions:
1. AFFiNE Alpha - The latest version in active development 
affine-self-hosted:latest
2. AFFiNE Pre-Alpha - Previous release which is no longer developed, but offers different functionality 
affine-self-hosted:pre-alpha
Simply swap out the Docker image for which version you require, the following instructions default to the latest image.
﻿
﻿
Installing AFFiNE using Docker

1. Pull the latest AFFiNE image. This may take some time depending on your network connection.

```
docker pull ghcr.io/toeverything/affine-self-hosted:latest
```

Ensure this step is completed successfully before continuing (you can rerun this command if you are unsure).
​
3. Next we will run the AFFiNE project in Docker.

```
docker run -it --name affine -d -v YOUR_PATH:/app/data -p 3000:3000 ghcr.io/toeverything/affine-self-hosted:latest
```

- (--name) Optional - this makes it convenient for using and interacting with your Docker container - such as docker restart affine.
- (-v) Optional - allows you to mount your data outside of Docker to your local machine. Remember to set YOUR_PATH to the directory of your choice.
- (-p) Required - this sets the port for where AFFiNE is running and listening, we use the default 3000 if you need to change this only change the first number e.g. [YOUR_PORT]:3000

Finally, the image id is the version of AFFiNE you wish to deploy. Following this guide, it would be the same as the previous step - so ghcr.io/toeverything/affine-self-hosted:latest
​
3. You can confirm that AFFiNE is running successfully by using the command
docker ps
This command shows a list of running containers - in the list you should be able to find AFFiNE.
﻿
﻿
Now you can access AFFiNE from your browser via:

If you are running Docker on your local machine and using the default settings you can access via port 3000 through localhost: http://localhost:3000/​

Otherwise you will need to know the {IP} of the machine using Docker and the {PORT} that AFFiNE is using.

Bear in mind that some features require a secure environment to work, which means https and wss connections through a reverse proxy setup. If you have any questions or need support you may want to try the Technical Discussion space.​
