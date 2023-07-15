# set_up_jupyter_lab
Install jupyterlab first
```
pip install jupyterlab
```
or install by conda
```
conda install -c conda-forge jupyterlab
```
# set up config
Use following cmd to generate a config file:
```
jupyter lab --generate-config
```
or replace the file with your own config file.

Generate your own password:
```
ipython
In [1]: from notebook.auth import passwd
In [2]: passwd()
```
or you can generate password in a jupyter_server_config.json file by
```
jupyter server password
```
and save your passwd to config file

# ipykernel
在base环境下运行jupyter lab可以访问所有环境的ipykernel~~（但是！cmd只在在jupyterlab运行的环境下执行）~~可以在kernel中运行以下代码实现在jupyter安装python包：
```
import sys 
!{sys.executable} -m pip install flask
```

在环境中安装ipykernel
```
conda install ipykernel
ipython kernel install --user --name=<env_name>
```
添加当前环境进入jupyter kernel（出现```ImportError: cannot import name 'secure_write' from 'jupyter_core.paths'```报错时，更换python版本或可解决）

In base, use cmd
```
jupyter kernelspec list
```
to check which env are in the kernel.
```
jupyter kernelspec remove <env_name>
```
to remove kernel

# shut down
Use following cmd to find the PID of which program taking this <port>.
```
lsof -i:<port>
```

# SSH remote connect#
```
ssh -N -f -L localhost:8889:localhost:8888 <username>@<remote_host>
```
其中： -N 告诉SSH没有命令要被远程执行； -f 告诉SSH在后台执行； -L 是指定port forwarding的配置，远端端口是8889，本地的端口号的8888。remote_user@remote_host 用实际的远程帐户和远程地址替换

Ref: [彻底搞懂SSH端口转发命令](https://zhuanlan.zhihu.com/p/148825449)

