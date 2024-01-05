# Acunetix Full awvs 23.x

## Acunetix for Windows using Docker

If you're looking to use Acunetix on your Windows machine, this repository provides a convenient solution using Docker. Below, you'll find step-by-step instructions on how to set it up.

The following repositories are quite useful: 

```
https://github.com/k4t3pr0/acunetix_v23.6/
https://github.com/XRSec/AWVS-Update 
```

## Prerequisites

- [Docker](https://www.docker.com/) must be installed on your Windows machine.

## Installation

### Step 1: Pull the Docker Image

Start by pulling the Docker image that contains the Acunetix files:

```bash
docker pull xrsec/awvs
```

### Step 2: Access the Docker Image

Access the Docker image with the following command:

```bash
docker exec -it awvs /bin/bash
apt update -y
apt upgrade -y
apt install libsqlite3-dev -y
```

### Step 3: Download the Activation Script

Inside the Docker image, download the script necessary to activate your Acunetix version:

```bash
wget https://www.fahai.org/aDisk/Awvs/check-tools.sh --no-check-certificate
```

### Step 4: Provide Execution Permissions

Grant execution permissions to the downloaded script:

```bash
chmod +x /check-tools.sh
```

### Step 5: Activate Acunetix

Finally, run the script to activate the full version of Acunetix:

```bash
./check-tools.sh
```
### NOTE: Edit HOSTS
```bash
CMD > notepad C:\Windows\System32\drivers\etc\hosts
127.0.0.1 awvs.lan
```
### RootCA 「must」

Downlaod && Install [`RootCA.cer`](https://cdn.jsdelivr.net/gh/XRSec/AWVS-Update@main/.github/resources/ca.cer)

### Visit Web

```ini
URL: https://awvs.lan:3443/#/login
UserName: awvs@awvs.lan
PassWord: Awvs@awvs.lan
```

## Usage

Once you've completed the installation, you should have a fully functional Acunetix setup on your Windows machine. Please note that any changes made within the Docker container may be lost if you decide to shut it down. In such cases, simply follow the installation steps again to reactivate Acunetix.

## Contribution

Feel free to contribute to this repository by opening issues or creating pull requests. Your contributions are highly appreciated.

