# Steve_NEXTFLOW

# NEXTFLOW practice


## Installation

## Java 11 version installation
Sincer Nextflow reuqired java version 1.8 or above and the Dockers requried java version 11.0 or above. 
go to following [link](https://www.oracle.com/kr/java/technologies/javase-jdk11-downloads.html) to dowoload Java that we are going to use

After installation, you can simply check Java version on terminal

```
java -version
```


## Conda

go to following [link](https://docs.conda.io/en/latest/miniconda.html) to dowonload miniconda

These Miniconda installers contain the conda package manager and Python. Once Miniconda is installed, you can use the conda command to install any other packages and create environments, etc. For example:
```
$ conda install numpy
...
$ conda create -n py3k anaconda python=3
...
```

For to update conda 
```
$ conda update conda
```

## Nextflow installation
To install Nextflow, you can simply download this workflow management by 
```
curl -s https://get.nextflow.io | bash
```

after installation, you can check whether this operate properly by
```
./nextflow run hello
```

## Singularity container installation
To install singularity container, you can use HOMEBREW or GUI tools to install.
Here, i am going to use HOMEBREW to install singularity container.

First install homebrew
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
Then, install virtural box by brew

```
brew install virtualbox
brew install vagrant
brew install vagrant-manager
```
And create and enter a directory to be used with your Vagrant VM.

```
mkdir vm-singularity
cd vm-singularity
```

lastly, issue the following commands to bring up the Virtual Machine
```
export VM=sylabs/singularity-3.0-ubuntu-bionic64
vagrant init $VM
vagrant up
vagrant ssh
```
***Note.if you have error when you do `vagrant up` you need to allow access vagrant-manager on your MAC by visiting  `system preferences` > `Security & Privacy` > `General`***

Finally, you can check up your singularity Version through

```
vagrant@vagrant:~$ singularity version
```

## Docker installation

To install Docker, you can simply download this through follwoing [link](https://www.docker.com/get-started)

the latest version is
```
Docker version 20.10.7, build f0df3501
```
you can check your docker version by
```
docker -v
```

### Docker Basic

**Here are some several commands that you might use frequently**

- `docker ps`: it will display all container list in docker daemon socket. Sometime, you get error (i.e. Got permission denied while trying to connect to the Docker....etc) this mean that the user has not permission to access this docker socket. if you have super user access you can use `sudo` to access this. 
  ```
  $ docker ps
  CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
  ```
  if you are super user you can add user access in the certain docker socket by 
  ```
  $ sudo usermod -aG docker $USERNAME
  $ sudo su - $USERNAME
  ```
- Lets pull example image (`centos`) to run container. in docker you can pull image by using command `docker pull Image_name` 
  ```
  $ docker pull centose
  Using default tag: latest
  latest: Pulling from library/centos
  8a29a15cefae: Pull complete
  Digest: sha256:fe8d824220415eed5477b63addf40fb06c3b049404242b31982106ac204f6700
  Status: Downloaded newer image for centos:latest
  docker.io/library/centos:latest
  ```
  you check pulled images through the command `docker images`
  ``` 
  $docker images
  REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
  centos              latest              470671670cac        8 weeks ago         237MB
  ```

**To process docker container, you need to do 2 step**
  1. from the docker resitorire, you need to pull docker image and download the image at locak
  2. through downloaded image, operatethe container. 

- To operate docker container, you can use `docker run` to operate container. Here i added option `-it` to run the shell.
  ```
  $ docker run -it centos:latest bash
  [root@d3fef9c0f9e9 /]#
  ```
- 
