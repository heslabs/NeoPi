# NEON


---
### Optimizing Generative AI on Arm Processors
https://github.com/arm-university/AI-on-Arm


---
### Setup

#### sudo apt install

```
sudo apt update
sudo apt upgrade -y
sudo apt install -y wget build-essential libssl-dev libbz2-dev libreadline-dev libsqlite3-dev zlib1g-dev libncurses5-dev libncursesw5-dev libffi-dev libgdbm-dev liblzma-dev uuid-dev tk-dev cmake
sudo apt install -y wget build-essential libssl-dev libbz2-dev libreadline-dev libsqlite3-dev zlib1g-dev libncurses5-dev libncursesw5-dev libffi-dev libgdbm-dev liblzma-dev uuid-dev tk-dev cmake
```


#### Install Python-3.12.0
```
wget https://www.python.org/ftp/python/3.12.0/Python-3.12.0.tgz
tar -xf Python-3.12.0.tgz
cd Python-3.12.0
./configure --enable-optimizations
sudo make altinstall
sudo make altinstall
## Python 3.12.0
```

#### Setup Python Virtual Environment

```
python3.12 -m venv aivenv
source aivenv/bin/activate
source aivenv/bin/activate
python3.12 -m pip install --upgrade numpy matplotlib pandas torch transformers jupyterlab ipykernel ipywidgets seaborn sentencepiece
```

