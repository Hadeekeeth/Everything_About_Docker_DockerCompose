# Docker Compose Installation using Compose plugin 

If you already have Docker Engine and Docker CLI installed, you can install the Compose plugin from the command line, by either:

## Step 1: To download and install the Compose CLI plugin, run:

```bash
DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
mkdir -p $DOCKER_CONFIG/cli-plugins
curl -SL https://github.com/docker/compose/releases/download/v2.29.6/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
```
## Step 2: Apply executable permissions to the binary:

```bash
chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose

```
 If you chose to install Compose for all users:
 
```bash
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose
```
 
## Step 3: Verify Docker Compose Installation
```bash
docker compose version
```
