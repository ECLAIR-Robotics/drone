# How to run WeBots Controllers in any Python Environment
Often the default WeBots libraries are not enough to implement RL models and we
need to add our own libraries. Here are the steps to allow you to run a WeBots
controller usuing a different Python environment

## Linux or WSL

1. Open the terminal and run the command `cd ~` to enter your home directory

2. Open up the .bashrc file inside your home directory with your favorite text editor and add the following lines at the end of the file.

  ```export WEBOTS_HOME=/usr/local/webots
     export LD_LIBRARY_PATH=$WEBOTS_HOME/lib/controller
  ```

  NOTE: If you downloaded webots with Snap you `WEBOTS_HOME` needs to be set to `/snap/webots/current/usr/share/webots` instead

3. Below the lines you added above, any these lines. 
  
  `export PYTHONPATH=$WEBOTS_HOME/lib/controller/python36`

  `export PYTHONIOENCODING=UTF-8`
