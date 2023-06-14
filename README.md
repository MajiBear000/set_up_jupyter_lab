# set_up_jupyter_lab
Install jupyterlab first
```
pip install jupyterlab
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
and save your passwd to config file
# ipykernel
在base环境下运行jupyter lab可以访问所有环境的ipykernel
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
jupyter kernelspec remove shun
```
to remove kernel

