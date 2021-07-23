# Steve_NEXTFLOW

# NEXTFLOW practice


## Installation

### Java 11 version installation
Sincer Nextflow reuqired java version 1.8 or above and the Dockers requried java version 11.0 or above. 
go to following [link](https://www.oracle.com/kr/java/technologies/javase-jdk11-downloads.html) to dowoload Java that we are going to use

After installation, you can simply check Java version on terminal

```
java -version
```


### Conda

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

### Nextflow installation
To install Nextflow, you can simply download this workflow management by 
```
curl -s https://get.nextflow.io | bash
```

after installation, you can check whether this operate properly by
```
./nextflow run hello
```

### Singularity container installation
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

### Docker installation
