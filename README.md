# Acunetix Full awvs 23.x

## Acunetix for Windows using Docker

![Acunetix Version](https://github.com/jesussuarz/Acunetix_Full_awvs_23.x/blob/e9372c4d62548f275f06ce8c8c653f13180702dc/Version.png)

If you're looking to use Acunetix on your Windows machine, this repository provides a convenient solution using Docker. Below, you'll find step-by-step instructions on how to set it up.

The following repositories are quite useful: 

```
https://github.com/XRSec/AWVS-Update
https://github.com/k4t3pr0/acunetix_v23.6/
```

## Prerequisites

- [Docker](https://docs.docker.com/desktop/install/windows-install/) must be installed on your Windows machine. (Docker Desktop)
- [Linux WSL2](https://learn.microsoft.com/en-us/windows/wsl/install) 
 
## Installation

### Step 1: Pull the Docker Image

Start by pulling the Docker image that contains the Acunetix files:

```cmd
CMD > docker pull xrsec/awvs
```

### Step 2: Access the Docker Image

Access the Docker image with the following command:

```cmd
CMD > docker exec -it awvs /bin/bash
```
Then, from the bash of your docker image run:

```bash
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
### NOTE: Edit the HOSTS file of your Windows machine
```bash
CMD > notepad C:\Windows\System32\drivers\etc\hosts
127.0.0.1 awvs.lan
```
### RootCA 「must」

Downlaod && Install [`RootCA.cer`](https://cdn.jsdelivr.net/gh/XRSec/AWVS-Update@main/.github/resources/ca.cer)
(this is installed in the browser of your Windows machine, for example in the root store of your Google Chrome or your Firefox)

### Visit Web

```ini
URL: https://awvs.lan:3443/#/login
UserName: awvs@awvs.lan
PassWord: Awvs@awvs.lan
```
![Acunetix Full](https://github.com/jesussuarz/Acunetix_Full_awvs_23.x/blob/e9372c4d62548f275f06ce8c8c653f13180702dc/Acunetix_full.png)

## Usage

Once you've completed the installation, you should have a fully functional Acunetix setup on your Windows machine. Please note that any changes made within the Docker container may be lost if you decide to shut it down. In such cases, simply follow the installation steps again to reactivate Acunetix.

## Contribution

Feel free to contribute to this repository by opening issues or creating pull requests. Your contributions are highly appreciated.

