# 🕵️ ExtremeAntiFingerprint

**ExtremeAntiFingerprint** is an **experimental, high-intensity browser fingerprint mutation engine** built on **Node.js + Puppeteer**.
It is designed for **advanced fingerprinting research, bot detection evasion testing, and defensive analysis** against modern anti-bot systems.

This project focuses on **aggressive entropy poisoning**, **multi-vector fingerprint mutation**, and **cluster-based browser execution**.

> ⚠️ This is **not** a stealth library for casual automation.
> It is intentionally extreme, noisy, and computationally heavy.

---

## 🧠 What This Project Does

* Launches **multiple Puppeteer browser workers**
* Mutates **browser fingerprints at runtime**
* Poisons:

  * Canvas
  * WebGL
  * AudioContext
  * Hardware metrics
  * Navigator APIs
* Rotates **User-Agent, screen size, hardware specs**
* Supports **Tor circuit rotation**
* Runs **continuously** in clustered attack loops

Used primarily for:

* Fingerprinting research
* Bot detection stress testing
* Anti-fingerprinting analysis
* Red-team automation experiments

---

## 🧱 Architecture Overview

```
Master Process
 ├─ Worker #0 ─ Puppeteer + Stealth + Noise
 ├─ Worker #1 ─ Puppeteer + Stealth + Noise
 ├─ Worker #2 ─ Puppeteer + Stealth + Noise
 └─ Worker #N ─ Puppeteer + Stealth + Noise
        ↓
   Fingerprint Mutation Engine
        ↓
   Target Website (test pages)
```

Each worker:

* Has **independent fingerprint mutations**
* Generates **unique canvas / WebGL entropy**
* Produces **screenshot proof artifacts**

---

## ✨ Core Features

### 🧬 Fingerprint Mutation

* Randomized **User-Agent pools** (Chrome & Firefox)
* Dynamic:

  * `navigator.platform`
  * `navigator.languages`
  * `navigator.hardwareConcurrency`
  * `navigator.deviceMemory`
* Screen resolution spoofing
* Color depth manipulation
* Touch point spoofing

---

### 🎨 Canvas Poisoning

* Micro-translation noise
* Pixel-level RGB mutation
* ImageData corruption
* Prevents stable canvas hashes

---

### 🎮 WebGL Poisoning

* Vendor spoofing
* Renderer spoofing
* Parameter mutation
* Prevents GPU fingerprint locking

---

### 🔊 AudioContext Poisoning

* OfflineAudioContext override
* Destination manipulation
* Sample rate mutation
* Noise injection

---

### ⏱ Timing & Memory Noise

* Random jitter & delay
* Fake memory availability
* Fake total system RAM

---

### 🧠 Puppeteer Stealth

* Uses:

  * `puppeteer-extra`
  * `puppeteer-extra-plugin-stealth`
* Disables:

  * WebRTC leaks
  * GPU acceleration
  * Background throttling
* Header randomization

---

### 🧵 Cluster Mode

* Auto-forks workers using `cluster`
* Auto-restart on worker crash
* Configurable worker count
* Designed for **long-running sessions**

---

### 🧅 Tor Circuit Rotation

* Uses Tor control port (`9051`)
* Sends `SIGNAL NEWNYM`
* Optional anonymity layer
* Works with SOCKS5 proxy setups

---


## 🛡️ Legal & Ethical Notice

This software is provided **for educational and research purposes only**.

You are responsible for:

* Compliance with local laws
* Website terms of service
* Ethical usage

The author assumes **no liability** for misuse.

---

## 🧪 Known Limitations

* Does NOT emulate real human input behavior
* Does NOT spoof TLS fingerprints
* Does NOT spoof TCP/IP stack
* Heavy CPU & memory usage
* High entropy ≠ realism

---

## 🧠 Intended Audience

* Anti-bot engineers
* Security researchers
* Red-team operators
* Fingerprinting researchers
* Detection system testers

---

## 📜 License

MIT License
Use at your own risk.

---

## 🧩 Final Notes

This project is **intentionally aggressive**.

# 🔥  Don't just copy it, make it better
