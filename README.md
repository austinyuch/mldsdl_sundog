# mldsdl_sundog
Machine learning, data science, Deep learning course practice, Udemy ccourse, by Frank Kane

https://www.udemy.com/course/data-science-and-machine-learning-with-python-hands-on/

## Environment preparation

### Python versioning
Python 3.6–3.9

1.
2.Install and then switch to version 3.9 (or later version if exists.)

Install pyenv (WSL2)
ref: https://github.com/pyenv/pyenv/wiki#suggested-build-environment  
```
sudo apt update; sudo apt install build-essential libssl-dev zlib1g-dev \
libbz2-dev libreadline-dev libsqlite3-dev curl \
libncursesw5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev

curl https://pyenv.run | bash
exec $SHELL
```

in ~/.bashrc, add: 
```
export PATH="$HOME/.pyenv/bin:$PATH"

if command -v pyenv 1>/dev/null 2>&1; then
 eval "$(pyenv init -)"
fi
```


check shims in path
```
echo $PATH | grep --color=auto "$(pyenv root)/shims"
```


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
for windows
```
get-command python
```
linux/WSL2
```
which python
```
or
```
python --version
```
create env
```
python -m pip install -U pip
python -m venv .venv

```

activate venv in windows
```
# switch to the python version
pyenv local 3.9.13
# upgrade pip
pip install -U pip
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
for linux:
```
python3 -m venv .venv
```

activate .venv
```
.venv/Scripts/activate
```
for linux
```
source ./.venv/bin/activate
```

```
pip install -U pip
```

do not use poetry, because jupyterlab dependency need cython; 
whiole Cython is a build dependency of pysam, but apparently pysam does not have a pyproject.toml 
ref:  
https://stackoverflow.com/questions/75372835/poetry-add-dependency-that-uses-cython  



(scipy Prerequisite)
sudo apt-get install build-essential gfortran libatlas-base-dev python-pip 
(ubuntu 22.04 has no python-dev)

pip install pandas
pip install jupyterlab
pip install scipy
pip install matplotlib
pip installl scilit-learn

### Tensorflow Docker
pull tensorflow docker
```
docker pull tensorflow/tensorflow:latest-gpu-jupyter
```

#### NVIDIA cuda for WSL2  
Ref: 
https://docs.nvidia.com/cuda/wsl-user-guide/index.html#getting-started-with-cuda-on-wsl  

```
sudo apt-key del 7fa2af80
```
會遇到
```
Warning: apt-key is deprecated. Manage keyring files in trusted.gpg.d instead (see apt-key(8)).
OK
```

## NVIDIA container toolkit
https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker

```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
      && curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
      && curl -s -L https://nvidia.github.io/libnvidia-container/$distribution/libnvidia-container.list | \
            sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
            sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
```

```
sudo apt-get update \
    && sudo apt-get install -y nvidia-container-toolkit-base
```

Download Installer for Linux WSL-Ubuntu 2.0 x86_64
(https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_local) 
```
wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-wsl-ubuntu.pin
sudo mv cuda-wsl-ubuntu.pin /etc/apt/preferences.d/cuda-repository-pin-600
wget https://developer.download.nvidia.com/compute/cuda/12.1.1/local_installers/cuda-repo-wsl-ubuntu-12-1-local_12.1.1-1_amd64.deb
```

```
sudo dpkg -i cuda-repo-wsl-ubuntu-12-1-local_12.1.1-1_amd64.deb
sudo cp /var/cuda-repo-wsl-ubuntu-12-1-local/cuda-*-keyring.gpg /usr/share/keyrings/
sudo apt-get update
sudo apt-get -y install cuda
```

#### cuDNN for WSL2
https://stackoverflow.com/questions/72493419/how-to-install-cudnn-in-ubuntu-on-wsl2  

// Only for linux, may not be valid in WSL2
https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html  



3.




enable long path  
https://thegeekpage.com/make-windows-11-accept-file-paths-over-260-characters/

https://media.sundog-soft.com/ml/MlCourse.zip


https://www.tensorflow.org/install/docker?hl=zh-tw
```
python -m venv venv 
pip install -r requirements.txt
```