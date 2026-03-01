# ⚡ I/O Data Transfer Techniques – Interactive Simulator  

> 🎓 Computer Architecture Project  
> A cycle-accurate, browser-based simulator for analyzing **Programmed I/O, Interrupt-Driven I/O, and DMA** performance.

---

[![GitHub Pages](https://img.shields.io/badge/Hosted%20on-GitHub%20Pages-blue?logo=github)](https://pages.github.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?logo=chartdotjs&logoColor=white)](https://www.chartjs.org/)

---

## 📑 Table of Contents

- [🌐 Live Demo](#-live-demo)
- [🧠 Project Overview](#-project-overview)
- [🌟 Why This Project Stands Out](#-why-this-project-stands-out)
- [📊 Techniques Compared](#-techniques-compared)
- [✨ Core Features](#-core-features)
- [📁 Project Structure](#-project-structure)
- [🚀 Deployment Guide](#-deployment-guide)
- [💻 Local Development](#-local-development)
- [⌨ Keyboard Shortcuts](#-keyboard-shortcuts)
- [🔬 Simulation Model](#-simulation-model)
- [📚 Academic Concepts Demonstrated](#-academic-concepts-demonstrated)
- [🛠 Tech Stack](#-tech-stack)
- [🎯 Learning Outcomes](#-learning-outcomes)
- [📄 License](#-license)
- [👨‍💻 Author](#-author)

---

## 🌐 Live Demo

👉 Hosted on GitHub Pages:

```
https://RishvinReddy.github.io/I-O-Data-Transfer-Techniques-Interactive-Simulator/
```

---

## 🧠 Project Overview

This web-based simulator models and compares three fundamental I/O data transfer techniques used in computer architecture:

- 🔄 **Programmed I/O (Polling)**
- ⚡ **Interrupt-Driven I/O**
- 🚀 **Direct Memory Access (DMA)**

The simulator performs:

- Cycle-level performance modeling  
- CPU utilization tracking  
- Interrupt overhead calculation  
- Throughput comparison  
- Break-even analysis  

All calculations run entirely in the browser using JavaScript — no backend required.

---

## 🌟 Why This Project Stands Out

### 🔍 Quantitative, Not Just Visual

Instead of stating “DMA is faster for large transfers,” this project proves it using:

- Total cycle counts  
- CPU utilization percentages  
- Throughput calculations  
- Speedup vs polling  
- Break-even thresholds  

This demonstrates analytical performance engineering.

---

### 🧠 Systems-Level Thinking

The simulator models:

- CPU cycle accounting  
- Interrupt Service Routine (ISR) overhead  
- Bus arbitration  
- DMA setup and completion costs  
- Scalability with increasing data size  

These are real computer architecture and operating system concepts — not just UI simulations.

---

### 📊 Built Like a Real Performance Tool

Includes:

- Real-time charts  
- CSV & JSON export  
- URL-based configuration sharing  
- Print-ready academic report mode  
- Configurable hardware parameters  

This mirrors how professional performance analysis tools work.

---

### 🚀 Strong Portfolio Signal

This project demonstrates:

- Hardware behavior modeling  
- Performance optimization analysis  
- Low-level systems understanding  
- Clean frontend engineering  
- Clear documentation  

Relevant for roles in:

- Embedded Systems  
- IoT  
- Firmware  
- Systems Programming  
- Operating Systems  
- Computer Architecture  

---

## 📊 Techniques Compared

| Technique | CPU During Transfer | Interrupts | Best For |
|------------|-------------------|------------|----------|
| 🔄 Programmed I/O | 100% Busy | 0 | Very small transfers |
| ⚡ Interrupt-Driven | ISR only | Per block | Medium transfers |
| 🚀 DMA | ~0% CPU | 1 completion | Large transfers |

---

## ✨ Core Features

### 🎮 Interactive Simulation Engine

- Run all techniques simultaneously  
- Step-by-step execution mode  
- Adjustable animation speed  
- Configurable parameters:
  - File size
  - Block size
  - CPU frequency (1–4 GHz)
  - Device speed
  - ISR overhead
  - DMA setup cycles  

---

### 📈 Real-Time Visualization

- CPU Utilization Line Chart  
- Throughput Comparison (MB/s)  
- Transfer Progress Tracker  
- Break-even Analysis Graph  
- Gantt Timeline (CPU busy vs idle)  
- Overhead Breakdown Chart  
- Radar Comparison Chart  

---

### 🖥 Architecture-Level Animations

- CPU, Memory, Disk Controller visualization  
- DMA controller behavior simulation  
- Memory grid heatmap  
- Bus packet animation  
- Oscilloscope-style CPU waveform  

---

### 🔧 Productivity Tools

- Dark / Light mode  
- Keyboard shortcuts  
- CSV export  
- JSON export  
- Shareable configuration links  
- Print-ready layout  
- Event log  

---

## 📁 Project Structure

```
github-pages/
├── index.html        # Main application
├── style.css         # Styling & themes
├── simulation.js     # Simulation engine logic
└── README.md         # Documentation
```

No build tools required. Fully static deployment.

---

## 🚀 Deployment Guide

### Deploy Entire Repository

```bash
git init
git add .
git commit -m "Initial commit – I/O Simulation"
git branch -M main
git remote add origin https://github.com/RishvinReddy/I-O-Data-Transfer-Techniques-Interactive-Simulator.git
git push -u origin main
```

Then:

GitHub → Settings → Pages → Source → `main` branch → root

---

## 💻 Local Development

### Python

```bash
python -m http.server 8765 --directory github-pages
```

Open:

```
http://localhost:8765
```

### Node

```bash
npx serve github-pages
```

---

## ⌨ Keyboard Shortcuts

| Key | Action |
|------|--------|
| R | Run simulation |
| S | Step mode |
| N | Next block |
| Esc | Reset |
| D | Toggle theme |
| C | Export CSV |
| ? | Help |

---

## 🔬 Simulation Model

### Scenario

Transfer `N` blocks of size `B` bytes from disk controller to main memory.

---

### 🔄 Programmed I/O

```
overhead_per_block = poll_cycles × 4
CPU_utilization = 100%
total_cycles = N × (poll_overhead + copy_cycles)
```

---

### ⚡ Interrupt-Driven I/O

```
overhead_per_block = ISR_entry + ISR_body + ISR_exit
total_cycles = N × (device_transfer + ISR_overhead + copy_cycles)
CPU_utilization = busy_cycles / total_cycles × 100
```

---

### 🚀 DMA

```
total_cycles = DMA_setup + device_transfer_all + completion_IRQ
CPU_utilization ≈ overhead / total_cycles × 100
```

---

### 📉 Break-Even Formula

```
N_break = ceil(DMA_total_overhead / ISR_per_block)
D_break = N_break × block_size
```

DMA becomes more efficient when:

```
data_size > D_break
```

---

## 📚 Academic Concepts Demonstrated

- Polling vs Interrupt I/O tradeoffs  
- ISR latency cost  
- DMA controller behavior  
- Bus arbitration  
- CPU cycle modeling  
- Performance scalability  
- Throughput vs utilization tradeoff  

---

## 🛠 Tech Stack

- HTML5  
- CSS3  
- Vanilla JavaScript  
- Chart.js  
- Canvas API  
- GitHub Pages  

No frameworks. No backend. Fully static.

---

## 🎯 Learning Outcomes

After using this simulator, students can:

- Explain differences between I/O techniques  
- Quantitatively compare performance  
- Derive break-even conditions  
- Understand interrupt scaling  
- Analyze CPU utilization behavior  

---

## 📄 License

Developed for academic and educational purposes as part of a Computer Architecture project.

---

## 👨‍💻 Author

**Erolla Rishvin Reddy**  
B.Tech – Computer Science  
Focus: Systems, Architecture, Embedded & Performance Engineering  

---
