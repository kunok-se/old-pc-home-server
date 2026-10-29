# Breathing New Life into a 15-Year-Old PC: Home Server & Website Deployment

Welcome to the story and technical guide of how a vintage 2011 laptop was transformed into a reliable, energy-efficient home server running **Ubuntu Linux** and **Docker**.

🌐 **Live GitHub Pages Documentation:** [https://kunok-se.github.io/old-pc-home-server](https://kunok-se.github.io/old-pc-home-server)

---

## 🖥️ The Hardware: Vintage 2011 Machine

Instead of sending an aging machine to e-waste, this project repurposes classic hardware into a dedicated local home server. 

### System Specifications
- **Hardware Model:** Dell Inspiron N4050 (Released ~2011 / ~15 years old)
- **Processor (CPU):** Intel® Core™ i5-2410M @ 2.30GHz (2 Cores, 4 Threads)
- **Memory (RAM):** 3.2 GiB
- **Storage:** 458 GB SSD/HDD Storage
- **Architecture:** x86_64

---

## 🐧 Operating System: Installing Ubuntu Linux

To turn this legacy laptop into a headless or lightweight server, **Ubuntu LTS** was chosen for its robust kernel support, extensive software ecosystem, and stability.

### Why Ubuntu LTS for Old Hardware?
1. **Low Resource Overhead:** Without a heavy desktop environment (running headless or minimal CLI), RAM usage sits at under 15% on idle.
2. **Modern Linux Kernel:** Excellent hardware compatibility and security updates.
3. **Docker-Ready:** Native support for containerization engines and Docker Compose.

---

## 📊 Performance Characteristics

Running server workloads on 15-year-old hardware proves that vintage machines still have immense utility:

```bash
$ free -h
               total        used        free      shared  buff/cache   available
Mem:           3.2Gi       2.0Gi       152Mi        20Mi       1.4Gi       1.2Gi
Swap:          3.7Gi       903Mi       2.8Gi

$ lscpu | grep "Model name"
Model name:                              Intel(R) Core(TM) i5-2410M CPU @ 2.30GHz
```

- **Idle RAM Usage:** ~500MB - 1GB (plenty of room for lightweight services).
- **Power Consumption:** Significantly lower than keeping a desktop workstation running 24/7.
- **Reliability:** Quiet operation and solid thermal performance for home automation, personal websites, and testing containers.

---

## 🐳 Containerization with Docker & Docker Compose

To run services cleanly and avoid dependency hell, **Docker** and **Docker Compose** were installed on the host.

### Key Container Services Hosted:
- **Home Website / Portfolio:** Static and dynamic web applications served via Nginx containers.
- **Automated Background Daemons:** Custom Python microservices for personal utilities and tracking.
- **Lightweight Databases:** SQLite-backed applications with persistent volume mapping.

### Quick Docker Setup Guide on Ubuntu:
1. Update system packages:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. Install Docker & Docker Compose:
   ```bash
   sudo apt install docker.io docker-compose-v2 -y
   ```
3. Enable and start Docker service:
   ```bash
   sudo systemctl enable --now docker
   ```
4. Verify installation:
   ```bash
   docker --version
   docker compose version
   ```

---

## 🚀 Conclusion

Repurposing a 15-year-old laptop into an Ubuntu & Docker home server is a rewarding, eco-friendly project. It proves that with Linux containerization, old hardware is more than capable of hosting personal websites, automation scripts, and self-hosted tools.

---

## 📄 License

MIT License. Feel free to use and adapt this guide for your own home lab projects!
