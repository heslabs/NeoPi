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
### Build

#### 1. Compile Kernels
```
mkdir -p bin
gcc -O0 -S -march=armv8-a+simd src/c/kernels/naive.c -o bin/naive.s
gcc -O3 -S -march=armv8-a+simd src/c/kernels/fp32_neon.c -o bin/fp32_neon.s
gcc -O3 -S -march=armv8-a+simd src/c/kernels/int8_neon.c -o bin/int8_neon.s
```

#### 2. Benchmarking Test

```
mkdir -p results
## Benchmarking - navie.c
gcc -O0 -S -march=armv8-a+simd src/c/kernels/naive.c -o bin/naive.s
gcc -O0 src/c/benchmark_naive.c -o bin/benchmark_naive -march=armv8-a+simd -lm ./bin/benchmark_naive

## fp32_neon.c
gcc -O3 -S -march=armv8-a+simd src/c/kernels/fp32_neon.c -o bin/fp32_neon.s
gcc -O3 -ffast-math src/c/benchmark_fp32_neon.c -o bin/benchmark_fp32_neon -march=armv8-a+simd -lm ./bin/benchmark_fp32_neon

## int8_neon.c
gcc -O3 -S -march=armv8-a+simd src/c/kernels/int8_neon.c -o bin/int8_neon.s
gcc -O3 -ffast-math src/c/benchmark_int8_neon.c -o bin/benchmark_int8_neon -march=armv8-a+simd -lm ./bin/benchmark_int8_neon
```

#### Plot Benchmarking

```
import matplotlib.pyplot as plt
import pandas as pd
# Load data from CSV files
naive_data = pd.read_csv('results/naive_latency_results.csv')
fp32_neon_data = pd.read_csv('results/fp32_neon_latency_results.csv')
int8_neon_data = pd.read_csv('results/int8_neon_latency_results.csv')

# Extract sizes and times
sizes = naive_data['mSize']
naive_times = naive_data['Latency(s)']
fp32_neon_times = fp32_neon_data['Latency(s)']
int8_neon_times = int8_neon_data['Latency(s)']

diffs0 = round(naive_times / naive_times)
diffs1 = round(naive_times / fp32_neon_times)
diffs2 = round(naive_times / int8_neon_times)

result = pd.concat([sizes, naive_times, diffs0, fp32_neon_times, diffs1, int8_neon_times, diffs2], axis=1)
print(result)
```


---
### Setup

#### 1. Install essential development packages

```
sudo apt update
sudo apt upgrade -y
sudo apt install -y wget build-essential libssl-dev libbz2-dev libreadline-dev libsqlite3-dev zlib1g-dev libncurses5-dev libncursesw5-dev libffi-dev libgdbm-dev liblzma-dev uuid-dev tk-dev cmake
sudo apt install -y linux-perf
```


#### 2. Install Python-3.12.0
```
wget https://www.python.org/ftp/python/3.12.0/Python-3.12.0.tgz
tar -xf Python-3.12.0.tgz
cd Python-3.12.0
./configure --enable-optimizations
sudo make altinstall
Python3 --version
## Python 3.12.0
```

#### 3. Setup Python Virtual Environment

```
python3.12 -m venv aivenv
source aivenv/bin/activate
python3.12 -m pip install --upgrade pip
python3.12 -m pip install --upgrade numpy matplotlib pandas torch transformers jupyterlab ipykernel ipywidgets seaborn sentencepiece
```

