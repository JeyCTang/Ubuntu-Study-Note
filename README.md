# Ubuntu-Study-Note
This note page is to record some tips while I am studying Ubuntu.
System version: Ubuntu 18.04

## 2019-12-31 HOW TO DECREASE THE SPEED OF CPU AND GPU FAN

I installed this system on my laptop.
This laptop has double graphic cards, one is intergrated intel card, the other one is GTX 1070.
So after the System installed successfully, the fan of my CPU and individual GPU card running very lound and abnormal. But the temperature isn't that high.

So after I looked for many posts on the internet. I concluded three ways  of sloving this problem. But I only used one simple way to slove this problem:
  1) Use command line to control and speed of CPU and GPU fan. I just roughly read it, I don't remember if we should install something before use the command. I think we have to install something first
  2) Download and install a software, I tried to find the software, but mainly there are some monitorning softwares, they are useful but cannot solve my problem directly. ALL I WANT IS JUST SLOW DOWN AND RUDUCE AND VOIDE
  3) __This one is queit useful, install the official GPU driver. Then open the driver and switch your primary GPU to intergrated graphics. Then log out, finally log in again. Then you will find your fan speed will decrease very soon.__
