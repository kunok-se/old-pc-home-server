# Breathing New Life into a 15-Year-Old Laptop: My Home Server & Website Journey

Welcome! If you have ever looked at an old, gathering-dust computer in your closet and wondered if it still had a pulse, this story is for you. Here is how I turned a vintage 15-year-old laptop into a proud, 24/7 energy-efficient home server running **Ubuntu Desktop** and **Docker**.

🌐 **Live GitHub Pages Documentation:** [https://kunok-se.github.io/old-pc-home-server](https://kunok-se.github.io/old-pc-home-server)

---

## 🏛️ The Patient: A 15-Year-Old Workhorse

Meet the hardware behind the project:
- **Model:** Dell Inspiron N4050 (Vintage 2011)
- **CPU:** Intel® Core™ i5-2410M @ 2.30GHz (2 Cores, 4 Threads)
- **RAM:** 3.2 GiB DDR3
- **Storage:** 500GB Western Digital HDD (**WDC WD5000BPVT-7**)

Instead of letting a perfectly capable machine end up as e-waste, I decided to give it a second career as a dedicated self-hosted lab.

---

## 🧩 The Plot Twist: When Ubuntu Server Couldn't Find the Hard Disk

Every good tech project has a moment of unexpected turns. When I first tried installing **Ubuntu Server** on this classic laptop, **the installer couldn't see the vintage hard drive at all!**

### The Solution
- **The Pivot:** Instead of getting stuck troubleshooting low-level storage drivers or BIOS controller modes on a 15-year-old motherboard, I switched to the **Ubuntu Desktop** installer.
- **The Result:** Ubuntu Desktop recognized the **Western Digital WDC WD5000BPVT-7 (500GB 2.5" SATA HDD)** out-of-the-box, allowing a smooth, hassle-free installation and setting up the foundation for a rock-solid home server.

---

## 📊 Performance & Benchmark Check

You might wonder: *Can a 15-year-old laptop running Ubuntu Desktop handle server workloads?* 

Let's look at the numbers:

### 1. System Resources
```bash
$ free -h
               total        used        free      shared  buff/cache   available
Mem:           3.2Gi       1.1Gi       152Mi        20Mi       1.9Gi       1.8Gi
```
Even with Ubuntu Desktop installed, idle RAM consumption hovers around **1.1 GB**, leaving plenty of breathing room for running Docker containers and web services.

### 2. Disk I/O Benchmark
Testing sequential write speeds on the vintage Western Digital SATA drive:
```bash
$ dd if=/dev/zero of=testfile bs=1M count=100 conv=fdatasync
100+0 records in
100+0 records out
100+857600 bytes (105 MB, 100 MiB) copied, 4.7 s, 22 MB/s
```
While it won't break any NVMe speed records, **22 MB/s** sequential write is more than enough for serving static websites, markdown documentation, and lightweight containerized workloads.

---

## 🐳 Bringing It to Life with Docker

To make software management painless, I installed **Docker** and **Docker Compose** on Ubuntu Desktop. Now, everything runs in isolated, portable containers.

### Quick Setup Commands on Ubuntu:
```bash
# Update system repositories
sudo apt update && sudo apt upgrade -y

# Install Docker & Docker Compose
sudo apt install docker.io docker-compose-v2 -y

# Enable and start service
sudo systemctl enable --now docker
```

---

## 🚀 Final Thoughts

Reviving a 15-year-old PC with **Ubuntu Desktop** and **Docker** into a home server is one of the most satisfying weekend projects. Bouncing from Ubuntu Server to Ubuntu Desktop turned out to be the magic key to getting past vintage hardware hurdles and giving this old machine a magnificent second act.

---

## 📄 License

MIT License. Feel free to fork and share your own vintage server adventures!
