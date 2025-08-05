# NeoPi


### Neoverse Edge Server: Hawkeye EDS-5410
* Key Features
   * 24-core Arm Neoverse-N2 Processors
   * 48GB ECC DDR5
   * Up to 2x 100GbE QSFP56 (with Break out Cable)
   * 1x 1GbE RJ45
   * 1x USB-C USB 3.0
   * 1x USB-C Consoles (Connect to Both CPU & MCU)
   * 1x USB-C USB 2.0 (Connect to MCU)
   * 1x m.2 M Key Connector for PCIe Extension

<img src="https://github.com/user-attachments/assets/f652e263-107c-4de1-b764-d62ad9b1eac1" width=350>

---
### Remote access to Neoverse edge server

```
$ sshpass -p <password> ssh cx10@192.168.72.10 -X
```


### Launch Chatbot with Gemma3-27B model

```
$ ssh cx10@192.168.72.10 -X
Password: xxxxx
$ cd ~/ollama-chat
$ ./run.sh
```

or 

```
$ cd ~/ollama-chat
$ ollama serve &
$ ollama run gemma3:27b $(cat ./quiz.txt)
```

#### quiz.txt
```
What is the difference between Cortex-A55 and Cortex-A53?
```

---
#### Chatbot response

```
root@hawkeye:~/ollama-chat# ollama run gemma3:27b $(cat ./quiz.txt)
Okay, let's break down the differences between the ARM Cortex-A55 and Cortex-A53 
processors. Both are designed for efficiency and are often found in mobile 
devices, IoT devices, and embedded systems, but the A55 is a significant 
improvement over the A53. Here's a detailed comparison:

**1. Architecture & Microarchitecture**

*   **Cortex-A53:** Based on the ARMv8-A architecture.  It's a 64-bit processor.  
It's an "out-of-order" execution processor, but a fairly simple one, focusing on 
power efficiency.
*   **Cortex-A55:**  Also based on ARMv8-A (and later ARMv8.1-A), but a *much* 
refined version.  It's specifically designed to maximize performance within a 
power budget, and is optimized for area. It's still an out-of-order processor, but 
has significant microarchitectural improvements.  It's often paired with the 
Cortex-A76 or Cortex-A78 for big.LITTLE configurations.

**2. Performance**

*   **Cortex-A53:**  Considered a good performer for its time, but is now 
considered relatively slow compared to newer cores.  It was the workhorse for many 
mid-range smartphones and tablets.
*   **Cortex-A55:**  **Significantly faster** than the A53.  ARM claims around a 
**20% performance improvement at the same power consumption**, or the same 
performance at a **reduced power consumption**. It delivers noticeably snappier 
performance in everyday tasks.  It's generally considered to be about 30-40% 
faster than the A53 in real-world scenarios.

**3. Efficiency (Power Consumption)**

*   **Cortex-A53:**  Good efficiency for its era.
*   **Cortex-A55:**  **More power efficient** than the A53. The improved 
microarchitecture allows it to do more work per watt. This is crucial for 
battery-powered devices. In some scenarios, it can reduce power consumption by up 
to 30% compared to the A53 while maintaining the same performance.

**4. Key Architectural Improvements in A55 (over A53)**

*   **Wider Decode:** The A55 can decode more instructions per cycle, allowing it 
to execute more instructions simultaneously.
*   **Improved Branch Prediction:**  More accurate branch prediction reduces 
pipeline stalls and improves performance.
*   **Larger Op Cache:**  A larger op cache stores more decoded instructions, 
reducing the need to fetch them from memory.
*   **Enhanced Data Prefetching:**  Better data prefetching brings data closer to 
the core, reducing memory latency.
*   **Improved Load/Store Unit:**  A more efficient load/store unit speeds up data 
access.
*   **Optimized Pipeline:**  Refinements to the instruction pipeline further 
improve performance.
*   **Scalability:**  The A55 is designed to be easily scaled, allowing 
manufacturers to use it in a wide range of configurations.
* **ARM Helium Technology:**  The A55 can benefit from ARM's Helium technology, 
which uses a wider range of vector instructions, enhancing its performance in 
multimedia and signal processing tasks.

**5. Use Cases**

*   **Cortex-A53:** Found in older smartphones (especially mid-range), tablets, set-top boxes, and early IoT devices^C

root@hawkeye:~/ollama-chat# ollama run gemma3:27b $(cat ./quiz.txt)
Both the Cortex-A55 and Cortex-A53 are ARM processors designed for efficiency, primarily found in mobile devices, embedded systems, and IoT devices. However, the Cortex-A55 
is a significant evolution over the A53. Here's a detailed breakdown of the differences:

**1. Architecture & Performance:**

* **Cortex-A53:** Based on the ARMv8-A architecture, introduced in 2012. It aimed to bring 64-bit computing to low-power devices.  It's a good performer for its time but 
shows its age now.
* **Cortex-A55:** Also based on ARMv8-A, but a *microarchitectural redesign*. Introduced in 2017, it's *not* a simple refresh. It focused on maximizing performance *within 
the same power envelope*.  Think of it as a ground-up re-engineering of the A53’s core principles.  It's significantly more efficient and provides better performance at the 
same power, or the same performance at lower power.

**Key Architectural Improvements in A55:**

* **Wider Decode:** The A55 can decode more instructions per cycle, boosting performance.
* **Improved Branch Prediction:**  Better prediction of which instruction will be executed next reduces stalls and improves efficiency.
* **Larger L1 Cache:**  The A55 has a larger L1 data cache, reducing memory access latency.
* **Improved Data Prefetching:**  Predicts what data the processor will need and fetches it in advance, reducing delays.
* **Optimized Pipeline:** A more efficient pipeline allows the processor to process instructions more quickly.
* **Larger Reorder Buffer:**  Allows more out-of-order execution, increasing instruction throughput.

**Performance Difference:**

* **Generally, the Cortex-A55 offers around 15-20% performance improvement over the Cortex-A53 at the same clock speed and power.**  This can vary depending on the specific 
implementation and workload.
* **More importantly, the A55 delivers much better performance *per watt*.**  This is crucial for battery-powered devices.

**2. Power Efficiency:**

* **Cortex-A53:**  Relatively efficient for its time but has higher power consumption compared to the A55 for similar performance.
* **Cortex-A55:**  Designed for extreme power efficiency.  It can deliver the same performance as the A53 with *much* lower power consumption, or more performance at the 
same power. This makes it ideal for devices where battery life is paramount.  It’s become the standard "little" core in many big.LITTLE configurations.

**3. Manufacturing Process & Typical Use Cases:**

* **Cortex-A53:** Was initially found on 28nm and 14nm processes.  Common in early 64-bit smartphones, tablets, and embedded systems.
* **Cortex-A55:**  Typically manufactured on 12nm, 7nm, or even 5nm processes, allowing for even greater efficiency and integration. It's very popular in:
    * **Modern Smartphones & Tablets:** Often used as the "little" core in big.LITTLE configurations paired with more powerful cores (like Cortex-A76, A78, or X2).
    * **Embedded Systems:**  Applications requiring low power and moderate performance.
    * **IoT Devices:**  Suitable for a wide range of connected devices.
    * **Automotive:** Infotainment systems, driver assistance features.



**4.  big.LITTLE Configuration:**

* Both cores are commonly used in big.LITTLE configurations, pairing high-performance cores (e.g., Cortex-A76, A78, X2) with efficiency-focused cores like the A53 or A55.
* **The A55 has largely *replaced* the A53 as the preferred "little" core** due to its superior efficiency.  The A55 allows devices to run simple tasks on the low-power 
core, saving battery, while seamlessly switching to the high-performance cores for demanding tasks.



**Here's a quick table summarizing the key differences:**

| Feature | Cortex-A53 | Cortex-A55 |
|---|---|---|
| **Architecture** | ARMv8-A (Initial) | ARMv8-A (Redesigned) |
| **Performance** | Moderate | 15-20% higher than A53 |
| **Power Efficiency** | Good for its time | Significantly better than A53 |
| **Cache (L1 Data)** | 32KB | 48KB |
| **Typical Use Cases** | Older smartphones, tablets, embedded systems | Modern smartphones, tablets, IoT, automotive |
| **Current Relevance** | Being phased out | Still widely used, preferred "little" core in big.LITTLE |



**In conclusion:**

The Cortex-A55 is a significant improvement over the Cortex-A53. It offers better performance, dramatically improved power efficiency, and is the preferred choice for modern 
low-power designs, especially in big.LITTLE configurations.  While the A53 was a good core in its time, the A55 has largely replaced it in new designs due to its superior 
characteristics.

root@hawkeye:~/ollama-chat# 
```
