# How to set up virtual environment on Ubuntu ___server___ for python development

_System: Ubuntu 18.04 LTS_

_Python version: Python 3.x_

## 1. Configure Python3

On Ubuntu 18.04, it has already installed python3.x and python2.x, although python 2.x is not supported by official anymore.

So first, let's update/upgrade softwares on Ubuntu.
```
$ sudo apt update
$ sudo apt -y upgrade
```
__-y means we agree all the options__

After this step, we can check the version of Python3.
```
$ python3 --version
```
For regulating the packages of python3, we should install pip, this tool will regulate and install packages we may use in python development.
```
$ sudo apt install -y python3-pip
```
__Here we use python3-pip because it's the pip on python3, don't forget we also installed python2 on our Ubuntu.__

After installation of pip, we also should install some additional tools and packages to guarantee the complete configuration of python3.
```
$ sudo apt install build-essential libssl-dev libffi-dev python3-dev
```

___Okay now we have done all the settings for a complete python3 development environment, in the next step we will set up a virtual environment___

## Set up virtual environment


Here we use __venv__ module, it's a part of python3 standard module lib. Here we install it as below:
```
$ sudo apt install -y python3-venv
```
After installation, we can create the virtual environment now. We can set up the virtual environment into an existing dictionary or make a new one, for example:
```
$ mkdir environments
$ cd environments
```
Then get into the dictionary, type below commends to create the virtual environment:
```
python3 -m venv __my_env__
```
___my_env is the name of virtual environment, obviously we can set with other names___

Then pyvenv will set up new dictionary named __my_env__, in this dictionary including some items, we can use 'ls' to check it:
```
$ ls my_env
bin include lib lib64 pyvenv.cfg share
```
These items will associate together to make the environment to separated from your system.

__Activate__ the environment to use it to work on your python development:
```
source my_env/bin/activate
```

Now at the head of your command in terminal, you will see your environment name in a block, that means it has been activated.
```
(my_env) xxxxxx:-/evnironments $
```

Now if we use the terminal to run and develop some python programs, the programs will be ran in the virtual environment instead of our system.

To stop the virtual environment, we can type ___deactivate___ or press ___ctrl+D___ on our keyboard.

___Note___: _Within the virtual environment, you can use the command python instead of python3, and pip instead of pip3 if you would prefer. If you use Python 3 on your machine outside of an environment, you will need to use the python3 and pip3 commands exclusively._

Original Link:

<https://www.jianshu.com/p/ab539e9a7955>

If you are going to set up a ___local programming environment___ for Python3. Steps are same. You can check the [Original essay link](https://www.digitalocean.com/community/tutorials/how-to-install-python-3-and-set-up-a-local-programming-environment-on-ubuntu-18-04) from here. 
