# mldsdl_sundog
Machine learning, data science, Deep learning course practice, Udemy ccourse, by Frank Kane

https://www.udemy.com/course/data-science-and-machine-learning-with-python-hands-on/

## Environment preparation

### Python versioning
Python 3.6–3.9

1.Install pyenv

2.Install and then switch to version 3.9 (or later version if exists.)

install pyenv 
for windows
```
Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"
```

```
pyenv install 3.9.13
pyenv local 3.9.13
pyenv rehash
pyenv shell 3.9.13
```

Env variable may be different, do check it. e.g. 
```
get-command python
```
or
```
python --version
```
create env
```
python -m pip install -U pip
python -m venv venv

```

activate venv in windows
```
# switch to the python version
pyenv local 3.9.13
# upgrade pip
python -m pip install -U pip
```
specify python path in vscode settings.json
```
{...
 "python.pythonPath": ".venv/Scripts/python",
...
}
```

create ".venv" venv
```
python -m venv .venv
```

activate .venv
```
.venv/Scripts/activate
```

```
pip install -U pip
```

Install poetry in Windows:
```
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -

```
or
```
pip install poetry
```
```
poetry init
```

pull tensorflow docker
```
docker pull tensorflow/tensorflow:latest-gpu-jupyter
```

NVIDIA cuda for WSL2

https://docs.nvidia.com/cuda/wsl-user-guide/index.html#getting-started-with-cuda-on-wsl

```
sudo apt-key del 7fa2af80
```
Download Installer for Linux WSL-Ubuntu 2.0 x86_64
(https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local) 
```
wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
sudo mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.1.1/local_installers/cuda-repo-wsl-ubuntu-12-1-local_12.1.1-1_amd64.deb
sudo dpkg -i cuda-repo-wsl-ubuntu-12-1-local_12.1.1-1_amd64.deb
sudo cp /var/cuda-repo-wsl-ubuntu-12-1-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cuda
```

3.




enable long path  
https://thegeekpage.com/make-windows-11-accept-file-paths-over-260-characters/

https://media.sundog-soft.com/ml/MlCourse.zip


https://www.tensorflow.org/install/docker?hl=zh-tw
```
python -m venv venv 
pip install -r requirements.txt
```