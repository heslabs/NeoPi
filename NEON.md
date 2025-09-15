# NeoPi NEON Benchmarks


---
### Optimizing Generative AI on Arm Processors
https://github.com/arm-university/AI-on-Arm

---
### Benchmarks

```
python3.12 ./bench_table.py
   mSize  Latency(s)  Latency(s)  Latency(s)  Latency(s)  Latency(s)  Latency(s)
0     32    0.000096         1.0    0.000006        16.0    0.000003        32.0
1     64    0.000757         1.0    0.000040        19.0    0.000020        38.0
2    128    0.006298         1.0    0.000340        19.0    0.000158        40.0
3    256    0.059910         1.0    0.007718         8.0    0.001367        44.0
4    512    0.481969         1.0    0.064720         7.0    0.029708        16.0
```

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

