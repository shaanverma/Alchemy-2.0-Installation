# Alchemy-2.0-Installation

## Tutorial for installing Alchemy 2.0 on Ubuntu

You can clone this repo and follow the steps, or you can download individual files as needed.

### Step 1
- Install Ubuntu 20.04.2 LTS (ISO above) on your computer or a virtual machine.

### Step 2
Update the sources repository using a text editor like vi as follow:

    sudo vi /etc/apt/sources.list

At the end of the file, just append the following lines:
    
    #gcc-4.4 g++-4.4 g++-4.4-multilib
    deb http://dk.archive.ubuntu.com/ubuntu/ trusty main universe
    deb http://dk.archive.ubuntu.com/ubuntu/ trusty-updates main universe
 
To save just type escape, and then enter :wq! to quit vi with saving mode.

To update the repository, just run the following command:

    sudo apt-get update

Now, to install gcc-4.4, just run the following commands:

    sudo apt-get install gcc-4.4 g++-4.4 g++-4.4-multilib
    
### Step 3

At this stage, you completed the setup of different versions of gcc and g++ in your OS. To select a default gcc and g++ compiler, we need to configure the alternative options of compilers through the following commands:

    sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-4.4 50
    sudo update-alternatives --install /usr/bin/g++ g++ /usr/bin/g++-4.4 50
    
To change the default gcc version, just run the command:

    sudo update-alternatives --config gcc

and select through the keypad (1, 2, 3, 4, etc.) the version of gcc and same for g++ as follow:

    sudo update-alternatives --config g++

### Step 4
Unzip and untar alchemy-2.tar.gz with:
    
    tar xvfz alchemy-2.tgz
    
This creates a directory alchemy-2 which contains the source code and documentation.

Next type the following 3 commands:

    cd alchemy-2/bin/
    make depend
    make

which will produce the executables learnstruct, learnwts, and infer in the directory alchemy-2/bin/.

And that's it!!!!!
