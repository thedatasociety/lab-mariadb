<!-- ds header -->
<div align="center">
 <img src="https://avatars3.githubusercontent.com/u/47368510?s=200&v=4" width="100px">
 <h3>The Data Science and Engineering Society </h3>
 <hr/>
</div>
<br/>
<!-- /ds header -->

# Sandbox for learning Relational Databases using Maria as an instance

This is binderhub-ready repository template for launching specific interfaces on [binderhub](https://github.com/jupyterhub/binderhub) instances while running a MongoDB server.

## Launching this repository on [binderhub](https://github.com/jupyterhub/binderhub) instances

[Binderhub](https://github.com/jupyterhub/binderhub) uses [repo2docker](https://github.com/jupyter/repo2docker) for launching and serving computational environments. Repo2docker supports multiple interfaces, such as [Jupyter](https://jupyter.org/), [JupyterLab](https://github.com/jupyterlab/jupyterlab), [VSCode](https://code.visualstudio.com), etc. [Mybinder.org](mybinder.org) is a public service for launching binder instances on a federation of Binderhub deployments.  Read more on [My Binder Federation](https://binderhub.readthedocs.io/en/latest/federation/federation.html).


The list below provides badges/hyperlinks for launching one of the interfaces on different binderhub instances.
    


#### JupyterLab 

- <a href="https://mybinder.org/v2/gh/thedatasociety/lab-mariadb/master?urlpath=lab" target="_blank">
      <img src="https://img.shields.io/badge/_launch_JupyterLab-@_mybinder.org-blue?logo=jupyter" alt="launch" >
  </a><br/><br/>

- <a href="https://binder.curvenote.dev/v2/gh/thedatasociety/lab-mariadb/master?urlpath=lab" target="_blank">
      <img src="https://img.shields.io/badge/_launch_JupyterLab-@_binder.curvenote.dev-blue?logo=jupyter" alt="launch" >
  </a><br/><br/>

- <a href="https://ovh.mybinder.org/v2/gh/thedatasociety/lab-mariadb/master?urlpath=lab" target="_blank">
      <img src="https://img.shields.io/badge/_launch_JupyterLab-@_ovh.mybinder.org-blue?logo=jupyter" alt="launch" >
  </a><br/><br/>

- <a href="https://ovh2.mybinder.org/v2/gh/thedatasociety/lab-mariadb/master?urlpath=lab" target="_blank">
      <img src="https://img.shields.io/badge/_launch_JupyterLab-@_ovh2.mybinder.org-blue?logo=jupyter" alt="launch" >
  </a><br/><br/>

- <a href="https://notebooks.gesis.org/binder/v2/gh/thedatasociety/lab-mariadb/master?urlpath=lab" target="_blank">
      <img src="https://img.shields.io/badge/_launch_JupyterLab-@_notebooks.gesis.org/binder-blue?logo=jupyter" alt="launch" >
  </a><br/><br/>


      
#### VSCode 

- <a href="https://mybinder.org/v2/gh/thedatasociety/lab-mariadb/master?urlpath=vscode/" target="_blank">
      <img src="https://img.shields.io/badge/_launch_VSCode-@_mybinder.org-blue?logo=coder" alt="launch" >
  </a><br/><br/>

- <a href="https://binder.curvenote.dev/v2/gh/thedatasociety/lab-mariadb/master?urlpath=vscode/" target="_blank">
      <img src="https://img.shields.io/badge/_launch_VSCode-@_binder.curvenote.dev-blue?logo=coder" alt="launch" >
  </a><br/><br/>

- <a href="https://ovh.mybinder.org/v2/gh/thedatasociety/lab-mariadb/master?urlpath=vscode/" target="_blank">
      <img src="https://img.shields.io/badge/_launch_VSCode-@_ovh.mybinder.org-blue?logo=coder" alt="launch" >
  </a><br/><br/>

- <a href="https://ovh2.mybinder.org/v2/gh/thedatasociety/lab-mariadb/master?urlpath=vscode/" target="_blank">
      <img src="https://img.shields.io/badge/_launch_VSCode-@_ovh2.mybinder.org-blue?logo=coder" alt="launch" >
  </a><br/><br/>


- <a href="https://notebooks.gesis.org/binder/v2/gh/thedatasociety/lab-mariadb/master?urlpath=vscode/" target="_blank">
      <img src="https://img.shields.io/badge/_launch_VSCode-@_notebooks.gesis.org/binder-blue?logo=coder" alt="launch" >
  </a><br/><br/>



### [Option 1] Launching this lab as a local container from a remote git repository using [repo2docker](https://github.com/jupyter/repo2docker)

1.  On a terminal, enter a folder of your preference and create a new Python virtual environment (venv):
```
python3 -m venv venv
``` 

3. Activate your virtual environment (you may do this again later if you want to restart your container):
```
source venv/bin/activate
```

4. Install/upgrade required Python libs using pip:
```
pip install jupyter-repo2docker pip -U
```

5. Launch the Docker container using `repo2docker` directly from the remote repository:

```bash
jupyter-repo2docker -p 8888:8888 https://github.com/thedatasociety/lab-mariadb \ 
                    jupyter lab --ip 0.0.0.0 --NotebookApp.token='mytoken'
```
Each interface will be available at a specific path, as follows:

* **JupyterLab**: http://127.0.0.1:8888/lab?token=mytoken

* **Jupyter**: http://127.0.0.1:8888/tree?token=mytoken

* **VSCode**:  http://127.0.0.1:8888/vscode?token=mytoken


See the [repo2docker](https://github.com/jupyter/repo2docker) documentation for more details [regarding the use of multiple interfaces](https://mybinder.readthedocs.io/en/latest/howto/user_interface.html) and other configs.    



### [Option 2] Launching this lab as a local container from a local git repository using [repo2docker](https://github.com/jupyter/repo2docker)


1. First, on a terminal, clone this git repository:

```bash
git clone https://github.com/thedatasociety/lab-mariadb.git
```

2.  Enter the repository folder (`cd lab-mariadb`) and create a new Python virtual environment (venv):
```
python3 -m venv venv
``` 

3. Activate your virtual environment (you may do this again later if you want to restart you container)
```
source venv/bin/activate

```

4. Install/upgrade required Python libs using pip:
```
pip install jupyter-repo2docker pip -U

```

5. launch the Docker container using repo2docker 


```bash 
jupyter-repo2docker -p 8888:8888 ./ jupyter lab --ip 0.0.0.0 --NotebookApp.token='mytoken'
```

If you want to map the local git folder inside the container, run
```bash
jupyter-repo2docker -p 8888:8888 -v $(pwd):$(echo ~)/host-folder \
                    ./ jupyter lab --ip 0.0.0.0 --NotebookApp.token='mytoken' 

```

Each interface will be available at a specific path, as follows:

* **JupyterLab**: http://127.0.0.1:8888/lab?token=mytoken

* **Jupyter**: http://127.0.0.1:8888/tree?token=mytoken

* **VSCode**:  http://127.0.0.1:8888/vscode?token=mytoken


### Attention 
Both repo2docker options above launch a container on port `8888`. Option 2 also creates a Docker volume that maps current local folder home into the container (`host-folder` folder inside the Jupyter Lab/Vscode context).

Before running it, make sure your local user is in the `docker` group. Please refer to this Docker [documentation](https://docs.docker.com/install/linux/linux-postinstall/) for more details. **It is strongly advised to not to run the container as root**. 
Please also be aware that the `--ip 0.0.0.0` is a directive that will start a sever which **will accept connections from any ip**. For security purposes the `--NotebookApp.token='mytoken'` directive forces the use of a security token for accessing any interface. Use `mytoken` to login or feel free to set a stronger token.

