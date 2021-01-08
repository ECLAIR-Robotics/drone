# How to run WeBots Controllers in any Python Environment
Often the default WeBots libraries are not enough to implement RL models and we
need to add our own libraries within a different Python environment. 
In order to do this we need to define some environmental variables ([Windows](https://www.digitalcitizen.life/simple-questions-what-are-environment-variables)/[Linux](https://opensource.com/article/19/8/what-are-environment-variables)/[Mac](https://medium.com/@himanshuagarwal1395/setting-up-environment-variables-in-macos-sierra-f5978369b255). Here are the steps to allow you to run a WeBots
controller using your own Python environment.

## Linux or Windows Subsystem for Linux (WSL)

1. Open the terminal and run the command `cd ~` to enter your home directory

2. Open up the .bashrc file inside your home directory with your favorite text editor (e.g. `nano .bashrc`, `code .bashrc`, `gedit .bashrc`, `vim .bashrc`) and add the following lines at the end of the file.

  ```
  export WEBOTS_HOME=/usr/local/webots
  export LD_LIBRARY_PATH=$WEBOTS_HOME/lib/controller
  ```

  NOTE: If you downloaded webots with Snap you `WEBOTS_HOME` needs to be set to `/snap/webots/current/usr/share/webots` instead

3. Below the lines you added above, add these lines to the bashrc. 
  
  ```
  export PYTHONPATH=$WEBOTS_HOME/lib/controller/python36
  export PYTHONIOENCODING=UTF-8
  ```
4. Close your terminal and open a new one (the variables are only set when you start a new process) 
5. Whenever you want to a control a robot, make sure it's controller field is set to `<extern>` 

<p align="center">
  <img src="/imgs/example.png" width="400">
</p>

6. Make sure you have opened the WeBots simulation you want. Now, you can execute the robot's control code from the terminal or any IDE of your choice!  
