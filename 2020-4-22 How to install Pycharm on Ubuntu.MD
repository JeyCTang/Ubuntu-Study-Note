# How to install Pycharm on Ubuntu

There are three ways to install this most popular IDE for python:
### 1. Install it from terminal
```
sudo apt install snapd snapd-xdg-open
sudo refresh
sudo snap install pycharm-community --classic
```
_I didn't even try this way because first it depends on the speed of your internet, secondly, you can't indicate the installation directory._

### 2. Install it from 'Ubuntu Software':

a.Search 'pycharm' in Ubuntu Software

![search pycharm in ubuntu Software]()

b.Choose to install Pycharm Pro/community

![Choose version]()

c. If your internet speed if good enough, this process is super easy. Just like how you install new apps on your cell phone or on windows. After you install it the desktop icon will automatically be in the system.

![Installation is done]()

___If you have good enough internet try this way, very easy___

### 3. Install it from Pycharm official website
a.Go to the pycharm official website to download the compressed package. professional version is recommended, we will crack it later.

b.After you download it, extract the package to where you wanna install pycharm.

c.Go into the extracted file and find bin/ file, open terminal in this file, then type:
```
./pycharm.sh
```
follow the steps finally you will open the pycharm IDE.

__However, there is a problem:__
You can't find the desktop icon on your graphical interfaces.
So we have to create a icon for it:

```
$ sudo vim /usr/share/applications/pycharm.desktop
```
We create a desktop file into this file. Then write contents as below into this file:
```
[Desktop Entry]
Name = Pycharm
Comment = Most popular IDE for python
Exec = /usr/local/pycharm/pycharm-professional-2020.1/bin/pycharm.sh
Icon = /usr/local/pycharm/pycharm-professional-2020.1/bin/pycharm.png
Terminal = False
Type = application
Categories = Application; Development; IDE; python
```
Items you must follow with above contents:
1. Type: To tell system what is it

Items you can type randomly on your own:
1. Name:
2. Comment;
3. Terminal: when you open the IDE the terminal wouldn't be opened too.
4. Categories

Items you must be noted and follow on your own computer:
1. Exec: this directory is where the extracted file located ( where the pycharm.sh file is )
2. Icon: Same with Exec, but it's where the pycharm.png is.

### 4. How to crack the professional version

It's simple, go to this website:
[link:]("https://zhile.io/2018/08/17/jetbrains-license-server-crack.html")

download the crack package from Baidu cloud disk. There is a instruction in the file (CN & EN version). Follow the step then you can crack it.
