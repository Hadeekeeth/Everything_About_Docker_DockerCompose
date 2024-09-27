# Docker Installation On Ubuntu Linux (Latest Version)

## Step 1: Uninstall Old Versions or conflicting packages
If you have any old versions of Docker installed, remove them using this command:

```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```
Also makesure Docker Engine Uninstalled
```bash
sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
```
Images, containers, volumes, or custom configuration files on your host aren't automatically removed. To delete all images, containers, and volumes:
```bash
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
```

## Step 2: Update Package Index and Install Dependencies

Update your system's package index and install the necessary dependencies for Docker:

```bash
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg lsb-release
```

## Step 3: Add Docker’s Official GPG Key

To ensure secure installation from Docker's official repository, add the Docker GPG key:

```bash
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

## Step 4: Set Up Docker’s Stable Repository

Add Docker’s stable repository to your system’s apt sources list:

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

## Step 5: Install Docker Engine

Update the package index again and install the latest version of Docker Engine and related components:

```bash
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

## Step 6: Verify Docker Installation
Check if Docker is installed correctly by verifying the version:

```bash
sudo docker --version
```

## Step 7: Manage Docker as a Non-Root User (Optional)
```bash
sudo usermod -aG docker $USER
```

## Step 8: Test Docker Installation
Run the following command to confirm Docker is working by running a test container:
```bash
sudo docker run hello-world
```

