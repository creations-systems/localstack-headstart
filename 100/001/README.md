

# 001 Install Docker

See also https://docs.docker.com/install/

## Install Docker on Linux Ubuntu

https://docs.docker.com/engine/install/ubuntu/


### Installation methods

You can install Docker Engine in different ways, depending on your needs:

1. Most users set up Docker’s repositories and install from them, for ease of installation and upgrade tasks. This is the recommended approach.

2. Some users download the DEB package and install it manually and manage upgrades completely manually. This is useful in situations such as installing Docker on air-gapped systems with no access to the internet.

3. In testing and development environments, some users choose to use automated convenience scripts to install Docker.

We concentrate on method 1:

#### 1. Install using the repository

Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

SET UP THE REPOSITORY

1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:

````
$ sudo apt-get update

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
````



more ...
