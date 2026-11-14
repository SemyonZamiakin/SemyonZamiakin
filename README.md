<p align="center">
  <img src="assets/banner.png" width="100%" alt="Background">
</p>

<h3 align="center">Semyon Zamyakin &nbsp;•&nbsp; <code>SIIMUCH</code></h3>

<p align="center">
  <em>Founder of Euclase &nbsp;|&nbsp; Systems & Low-Level Engineer</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C++17-%2300599C.svg?style=flat&logo=c%2B%2B&logoColor=white&color=161b22" alt="C++">
  <img src="https://img.shields.io/badge/C-%2300599C.svg?style=flat&logo=c&logoColor=white&color=161b22" alt="C">
  <img src="https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54&color=161b22" alt="Python">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black&color=161b22" alt="Linux">
  <img src="https://img.shields.io/badge/Windows-0078D6?style=flat&logo=windows&logoColor=white&color=161b22" alt="Windows">
  <img src="https://img.shields.io/badge/Assembly-%236E4C13.svg?style=flat&logo=assemblyscript&logoColor=white&color=161b22" alt="Assembly">
</p>

---

### Core Projects

| Project | Description | Stack | Status |
| :--- | :--- | :--- | :--- |
| **[Vajra Binary Core](https://github.com/SemyonZamiakin/VajraBinaryCore)** | Runtime binary patching and live memory layout migration engine for native C++ binaries. | C++17, x86-64, Linux, Windows | `v0.1.0` (75 tests, CI) |
| **[Corundum HFT](https://github.com/SemyonZamiakin/CorundumHFT)** | Zero-copy lock-free SPSC ring buffer in POSIX shared memory for low-latency telemetry. | C11, C++17, Linux, Windows | `v1.1.0` (129 tests, CI) |
| **[Euclase SessionGuard](https://github.com/SemyonZamiakin/EuclaseSessionGuard)** | Tamper-evident local audit daemon for desktop applications and messaging sessions. | Python 3.11+, Windows, Linux | `v0.2.0` (129 tests) |
| **[Euclase Monitor](https://github.com/SemyonZamiakin/Euclase Monitor)** | Tray system monitor with skinnable GDI+ overlay publishing to Corundum shared memory. | C++17, Win32, GDI+ | `v1.1.0` (Tested) |
| **[Euclase Light](https://github.com/SemyonZamiakin/EuclaseLight)** | Lightweight C++ core & WPF RGB lighting control panel linked with system telemetry. | C++17, .NET 10, WPF | `v1.0.0` (Verified) |
| **[EuclaseUI](https://github.com/SemyonZamiakin/EuclaseUI)** | Minimal UI toolkit for SPI TFT displays featuring dirty-rectangle flushing. | C++11, ESP32, Arduino | `v0.1.0` (Embedded) |

> *The projects build on each other: Euclase Monitor publishes metrics over Corundum HFT, and Euclase Light reads them to drive hardware states.*

---

### Engineering Approach

* **Rigorous Testing:** Every subsystem comes with automated test suites and CI pipelines (ASan, UBSan, ThreadSanitizer).
* **Differential Verification:** Decoders and parsers are cross-validated against reference tools (e.g., custom x86-64 decoder checked against GNU `objdump`).
* **Zero Bloat:** Lightweight, terminal-first, open-source code built directly via GCC/CMake without heavy third-party runtime dependencies.
* **Security First:** Local-only loops, pinned checksums, and zero telemetry leakage off the machine.

---

### Contact & Status

* **Email:** `semyanzamyakin3@gmail.com`
* **Telegram:** [@SIIMUCH](https://t.me/SIIMUCH)
* **Discord:** `SIIMUCH` (`832983105287618601`)

*Status:* Available for technical co-founder / CTO roles in high-performance or systems-level product teams.
