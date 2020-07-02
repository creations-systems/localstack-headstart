

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

2. Add Docker’s official GPG key:

````
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
````

Verify that you now have the key with the fingerprint (may differ from yours)

````
9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
````
, by searching for the last 8 characters of the fingerprint.

````
$ sudo apt-key fingerprint 0EBFCD88

pub   rsa4096 2017-02-22 [SCEA]
      9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
sub   rsa4096 2017-02-22 [S]
````

3. Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below. Learn about nightly and test channels.

***Note***: The lsb_release -cs sub-command below returns the name of your Ubuntu distribution, such as xenial. Sometimes, in a distribution like Linux Mint, you might need to change $(lsb_release -cs) to your parent Ubuntu distribution. For example, if you are using Linux Mint Tessa, you could use bionic. Docker does not offer any guarantees on untested and unsupported Ubuntu distributions.

x86_64 / amd64   <== THIS IS US
````
$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
````

OR

armhf
````
$ sudo add-apt-repository \
   "deb [arch=armhf] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
````

OR

arm64
````
$ sudo add-apt-repository \
   "deb [arch=arm64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
````

INSTALL DOCKER ENGINE

1. Update the apt package index, and install the latest version of Docker Engine and containerd, or go to the next step to install a specific version:

````
 $ sudo apt-get update
 $ sudo apt-get install docker-ce docker-ce-cli containerd.io
````

NOTE: Got multiple Docker repositories?

If you have multiple Docker repositories enabled, installing or updating without specifying a version in the apt-get install or apt-get update command always installs the highest possible version, which may not be appropriate for your stability needs.




more ...
