<h1> Set virtual environment for python3 on Ubuntu and how to use it</h1>

___system: Ubuntu 18.04 LTS___

___python 3.x___

This essay we will set up virtual environment through installing virtualenv on Ubuntu 18.04
instead of through __venv__.

* [1. Install virtualenv](#1)

* [2. Install regulation tool: Virtualenvwrapper](#2)

* [3. How to use virtualenvwrapper to regulate your virtual environment](#3)
  * [3.1 mkvirtualenv](#3.1)
  * [3.2 workon](#3.2)
  * [3.3 leave virtual environment](#3.3)
  * [3.4 delete environment](#3.4)
  * [3.5 list environments](#3.5)
  * [3.6 packages conrol](#3.6)
  * [3.7 copy environment](#3.7)
  * [3.8 Execute commands on env](#3.8)
  * [3.9 create temporary env](#3.9)
  * [3.10 show virtualenv ](#3.10)
  * [3.11 enter virtualenv dir](#3.11)
  * [3.12 change virtualenv dir](#3.12)
  * [3.13 list packages of virtualenv](#3.13)
  * [3.14 create new project dir and link it](#3.14)
  * [3.15 link an existing project and virtualenv](#3.15)
  * [3.16 switch current dir to a project dir ](#3.16)
  * [3.17 delete all the third party packages ](#3.17)
  * [3.18 Help manuals](#3.18)

<h2 id="1"> 1. Install virtualenv</h2>

```
$ pip3 install virtualenv
```

__NOTE:__ You have to install pip before you execute this command.


<h2 id="2"> 2. Install regulation tool: Virtualenvwrapper </h2>

```
$ sudo pip3 install virtualenvwrapper
```

Till now, we still can't use Virtualenvwrapper, we have configure some settings as below:
1. Create a new dictionary to store virtual environment:
```
mkdir ~/.virtualenvs
```
2. Editing ~/.bashrc file.
```
vim ~/.bashrc
```
Add contents at the tail of .bashrc:
```
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/Devel
source /usr/local/bin/virtualenvwrapper.sh
```
3. Save and quit:
```
:wq:
```
After this step we run command:
```
$ source ~/.bashrc
```
Here we might meet problem as below:
```
/usr/bin/python: No module named virtualenvwrapper
virtualenvwrapper.sh: There was a problem running the initialization hooks.
If Python could not import the module virtualenvwrapper.hook_loader,
check that virtualenvwrapper has been installed for
VIRTUALENVWRAPPER_PYTHON=/usr/bin/python and that PATH is
set properly.
```
Read it, it's easily to understand.
You have to edit the cofiguration file and path correctly.
Editing .bashrc, add one more contents:
```
export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3
```
Then execute again:
```
source ~/.bashrc
```
It will shows similar as below:
```
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/premkproject
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/postmkproject
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/initialize
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/premkvirtualenv
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/postmkvirtualenv
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/prermvirtualenv
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/postrmvirtualenv
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/predeactivate
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/postdeactivate
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/preactivate
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/postactivate
virtualenvwrapper.user_scripts creating /home/jey/.virtualenvs/get_env_details
```
Now the setting up and installation is completely finished.

<h2 id="3">3. How to use virtualenvwrapper to regulate your virtual environment</h2>

<h3 id="3.1">3.1 mkvirtualenv [-a project_path] [-i package] [-r requirements_file] [virtualenv options] ENVNAME</h3>

* The -a option can be used to associate an existing project directory with the new environment.

* The -i option can be used to install one or more packages (by repeating the option) after the environment is created.

* The -r option can be used to specify a text file listing packages to be installed. The argument value is passed to pip -r to be installed.

<h3 id="3.2">3.2 Use virtual environment</h3>

When we wanna use virtual environment, we can use command:

```
$ workon ENVNAME
```

Funtions of workon:

* workon [ENVNAME]: switch various envs
* workon : list all the environments which are stored in $HOME/.virtualenvs

<h3 id="3.3">3.3 Leave virtual environment </h3>

```
$ deactivate
```

<h3 id="3.4">3.4 Delete virtual environment </h3>

```
rmvirtualenv venvname
```

<h3 id="3.5">3.5 Show the list of virtual environments</h3>

```
workon
```
or
```
lsvirtualenv
```

<h3 id="3.6">3.6 Control virtual environment of using global site-packages</h3>

```
toggleglobalsitepackages
```

<h3 id="3.7">3.7 duplicate environment</h3>

```
$ cpvirtualenv [source][dest]
$ cpvirtualenv env1 env3
```

<h3 id="3.8">3.8 Execute commands on all environments stored in WORKEN_HOME</h3>

```
$ allvirtualenv pip install -U pip3
```

<h3 id="3.9">3.9 Create a temporary environment</h3>

when you type 'deactivate', this environment will be deleted.

```
$ mktmpenv
```

<h3 id="3.10">3.10 showvirtualenv[env]</h3>

Show the details for a single virtualenv.

<h3 id="3.11">3.11 cdvirtualenv[subdir]</h3>

此时在一个虚拟环境中，改变当前工作目录到该虚拟环境所在目录，如果后面加subdir，则直接进入虚拟环境下的子目录。

Now you should be in the env, change the current working dictionary to current virtualenv, if you add subdir, then step into subdir of virtualenv.

<h3 id="3.12">3.12 cdsitepackages[subdir]</h3>

改变当前工作目录到 site-packages for $VIRTUAL_ENV.

Change current working dir to $VIRTUAL_ENV.

<h3 id="3.13">3.13 lssitepackages</h3>

列出当前激活的虚拟环境site-packages中的文件及子目录

<h3 id="3.14">3.14 mkproject</h3>

```
mkproject [-f|--force] [-t template] [virtualenv_options] ENVNAME
```

创建一个新的虚拟环境在WORKON_HOME 和工程目录在PROJECT_HOME，工程目录与虚拟环境绑定，每次workon ENVNAME 直接使用python虚拟环境在项目目录下工作

```
-f, --force Create the virtualenv even if the project directory already exists
```

<h3 id="3.15">3.15 setvirtualenvproject [virtualenv_path project_path]</h3>

将一个已经存在的虚拟环境和已经存在的工程绑定，每次workon ENVNAME 直接使用python虚拟环境在绑定项目目录下工作

<h3 id="3.16">3.16 cdproject </h3>

改变当前工作目录到一个具体的工程目录 for the active virtualenv.

<h3 id="3.17">3.17 wipeenv </h3>

删除当前虚拟环境中安装的所有的第三方包

<h3 id="3.18">3.18 virtualenvwrapper</h3>

打印virtualenvwrapper支持的命令和命令描述作为简单的帮助文档
