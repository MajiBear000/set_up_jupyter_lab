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
