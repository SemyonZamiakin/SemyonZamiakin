<p align="center">
  <img src="assets/banner.png" width="100%" alt="Semyon Zamiakin, founder of Euclase: systems-level software">
</p>

<h3 align="center">Semyon Zamyakin &nbsp;•&nbsp; <code>SIIMUCH</code></h3>

<p align="center">
  <em>Founder of Euclase &nbsp;|&nbsp; Systems & Low-Level Engineer</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B17-0F2933?style=for-the-badge&logo=cplusplus&logoColor=2DD4BF" alt="C++17">
  <img src="https://img.shields.io/badge/C11-0F2933?style=for-the-badge&logo=c&logoColor=2DD4BF" alt="C11">
  <img src="https://img.shields.io/badge/Python-0F2933?style=for-the-badge&logo=python&logoColor=2DD4BF" alt="Python">
  <img src="https://img.shields.io/badge/C%23%20%2F%20.NET-0F2933?style=for-the-badge&logo=dotnet&logoColor=2DD4BF" alt="C# / .NET">
  <img src="https://img.shields.io/badge/x86--64-0F2933?style=for-the-badge" alt="x86-64">
  <img src="https://img.shields.io/badge/Linux-0F2933?style=for-the-badge&logo=linux&logoColor=2DD4BF" alt="Linux">
  <img src="https://img.shields.io/badge/Windows-0F2933?style=for-the-badge" alt="Windows">
  <img src="https://img.shields.io/badge/CMake-0F2933?style=for-the-badge&logo=cmake&logoColor=2DD4BF" alt="CMake">
</p>

<p align="center">
I write software that works close to the machine: an LLM engine whose SIMD kernels are written by hand, code that patches a running program's machine code, lock-free IPC
measured in nanoseconds, monitors that read the operating system directly, and UI for small embedded displays.
Everything is open source under the <b>Euclase</b> name, and every repository says plainly what is tested and what is not.
</p>

<p align="center"><img src="assets/divider.png" width="100%" alt=""></p>

<h3 align="center">In numbers</h3>

<table align="center">
  <tr>
    <td align="center" width="20%">
      <h2>74 ns</h2>
      <sub>one-way message between two processes through <b>Corundum HFT</b> on Windows<br>(an OS pipe: 6.7 µs)</sub>
    </td>
    <td align="center" width="20%">
      <h2>2M+</h2>
      <sub>real x86-64 instructions where <b>Vajra</b>'s own decoder matches GNU objdump</sub>
    </td>
    <td align="center" width="20%">
      <h2>1.3 ms</h2>
      <sub>per update in <b>Euclase Monitor</b> 1.1<br>(8.1 ms in 0.1)</sub>
    </td>
    <td align="center" width="20%">
      <h2>0</h2>
      <sub>network connections opened by <b>SessionGuard</b>: the audit log never leaves your PC</sub>
    </td>
    <td align="center" width="20%">
      <h2>38.8 tok/s</h2>
      <sub>a 1.1B-parameter LLM on an i9-9900K CPU with <b>Adamant</b>'s hand-written AVX2</sub>
    </td>
  </tr>
</table>

<p align="center"><img src="assets/divider.png" width="100%" alt=""></p>

<h3 align="center">Projects</h3>

<table>
  <tr>
    <td colspan="2" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/Adamant">Adamant SIMD-VIC</a> &nbsp;<sub>new</sub></h3>
      <p><em>A large language model on your CPU, with every hot loop written by hand.</em></p>
      <p>Loads a quantized LLM from a GGUF file through a zero-copy memory mapping and generates text with hand-written AVX2
      kernels for the Q4_K, Q6_K and Q8_0 block formats, each bit-identical to its scalar twin: same logits, same tokens.
      Generated tokens stream to other programs over a Corundum ring; a live console view shows tokens per second and
      per-core load from Euclase Monitor.</p>
      <p>
        <img src="https://img.shields.io/badge/version-0.1.0-2DD4BF?labelColor=0F2933" alt="version 0.1.0">
        <a href="https://github.com/SemyonZamiakin/Adamant/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/Adamant/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/C%2B%2B17%20%2B%20AVX2-Linux%20%7C%20Windows-2DD4BF?labelColor=0F2933" alt="C++17 + AVX2, Linux, Windows">
      </p>
      <sub>TinyLlama-1.1B: 38.8 tok/s on Windows, 45 on Linux (i9-9900K, 8 threads) · logits match an independent numpy reference (cosine 0.9998) · 3.8 M kernel results checked bit for bit · ASan + UBSan, TSan</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/VajraBinaryCore">Vajra Binary Core</a></h3>
      <p><em>Hot-patch a running C++ program without restarting it.</em></p>
      <p>Replaces machine code (entry trampolines, GOT/PLT and IAT redirection) and migrates live objects to a new struct
      layout with every pointer fixed up, all in one atomic transaction that can be reverted. Ships its own x86-64
      instruction decoder and relocator.</p>
      <p>
        <img src="https://img.shields.io/badge/version-0.1.0-2DD4BF?labelColor=0F2933" alt="version 0.1.0">
        <a href="https://github.com/SemyonZamiakin/VajraBinaryCore/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/VajraBinaryCore/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/C%2B%2B17-Linux%20%7C%20Windows-2DD4BF?labelColor=0F2933" alt="C++17, Linux, Windows">
      </p>
      <sub>75 tests in 11 suites · fault injection at every write · stress tests patching while 8 threads run · ASan + UBSan, TSan on the cooperative paths</sub>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/CorundumHFT">Corundum HFT</a></h3>
      <p><em>Zero-copy IPC for high-frequency telemetry.</em></p>
      <p>A lock-free single-producer / single-consumer ring buffer in shared memory. The writer builds a message in place,
      the reader uses it in place: one acquire load and one release store per side, no system calls, locks or heap on the
      hot path. Linux (POSIX shm + futex) and Windows (named mapping + event).</p>
      <p>
        <img src="https://img.shields.io/badge/version-1.2.0-2DD4BF?labelColor=0F2933" alt="version 1.2.0">
        <a href="https://github.com/SemyonZamiakin/CorundumHFT/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/CorundumHFT/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/C11%20%2F%20C%2B%2B17-Linux%20%7C%20Windows-2DD4BF?labelColor=0F2933" alt="C11 / C++17, Linux, Windows">
      </p>
      <sub>~970 checks · 3 million records verified across processes · CI on Linux x86-64, arm64 and Windows with sanitizers</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/EuclaseSessionGuard">Euclase SessionGuard</a></h3>
      <p><em>Did anyone use my messengers while I was away?</em></p>
      <p>Watches Telegram, Discord, Viber, Signal, Slack and the browsers that hold your social logins: when each one ran,
      used the network and had focus, who touched its session files, logons and unlocks, and anything during your quiet
      hours. Every record is signed and chained, so edits and deletions are detected.</p>
      <p>
        <img src="https://img.shields.io/badge/version-0.2.0-2DD4BF?labelColor=0F2933" alt="version 0.2.0">
        <a href="https://github.com/SemyonZamiakin/EuclaseSessionGuard/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/EuclaseSessionGuard/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/Python%203.11%2B-Windows%20%7C%20Linux-2DD4BF?labelColor=0F2933" alt="Python 3.11+, Windows, Linux">
      </p>
      <sub>129 tests · CI on Windows, Linux and macOS · no third-party packages · Windows file-audit mode not yet run live</sub>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/EuclaseMonitor">Euclase Monitor</a></h3>
      <p><em>A system monitor you can reshape with one text file.</em></p>
      <p>Tray app for Windows with a skinnable overlay: CPU, GPU, RAM and network, skins in JSON with hot reload.
      Version 1.1 asks the OS only for what the skin shows, caches what never changes, and publishes every snapshot to
      other programs over a Corundum ring.</p>
      <p>
        <img src="https://img.shields.io/badge/version-1.1.0-2DD4BF?labelColor=0F2933" alt="version 1.1.0">
        <a href="https://github.com/SemyonZamiakin/EuclaseMonitor/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/EuclaseMonitor/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/C%2B%2B17-Win32%20%7C%20GDI%2B-2DD4BF?labelColor=0F2933" alt="C++17, Win32, GDI+">
      </p>
      <sub>~420 KB exe · about half the CPU of 0.1 · unit tests, tested docs and end-to-end tests of the real exe</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/EuclaseLight">Euclase Light</a></h3>
      <p><em>One app for all your RGB.</em></p>
      <p>Graphics card, RAM, motherboard and anything else OpenRGB supports, with a live preview and a write-protection layer
      for memory buses. Version 1.1 lets the colours follow CPU or GPU load, read from Euclase Monitor ten times a second.</p>
      <p>
        <img src="https://img.shields.io/badge/version-1.1.0-2DD4BF?labelColor=0F2933" alt="version 1.1.0">
        <a href="https://github.com/SemyonZamiakin/EuclaseLight/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/EuclaseLight/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/C%2B%2B17%20%2B%20WPF-.NET%2010-2DD4BF?labelColor=0F2933" alt="C++17 + WPF, .NET 10">
      </p>
      <sub>68 core checks · verified on the author's PC · load-driven colour not yet tested on hardware</sub>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/SemyonZamiakin/EuclaseUI">EuclaseUI</a></h3>
      <p><em>Smooth UI on cheap SPI displays.</em></p>
      <p>A dependency-free UI toolkit for ESP32 / Arduino with ST7789 and ILI9341 panels. It tracks which rectangles changed
      and sends only those over SPI, with no heap allocation.</p>
      <p>
        <img src="https://img.shields.io/badge/version-0.1.0-2DD4BF?labelColor=0F2933" alt="version 0.1.0">
        <a href="https://github.com/SemyonZamiakin/EuclaseUI/actions/workflows/ci.yml"><img src="https://github.com/SemyonZamiakin/EuclaseUI/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
        <img src="https://img.shields.io/badge/C%2B%2B11-ESP32%20%7C%20Arduino-2DD4BF?labelColor=0F2933" alt="C++11, ESP32, Arduino">
      </p>
      <sub>38 host checks · host simulator · not yet verified on real hardware</sub>
    </td>
  </tr>
</table>

<h3 align="center">How they fit together</h3>

```mermaid
%%{init: {'theme': 'base', 'themeVariables': {'primaryColor': '#0F2933', 'primaryTextColor': '#F8FAFC', 'primaryBorderColor': '#2DD4BF', 'lineColor': '#2DD4BF', 'edgeLabelBackground': '#0F2933', 'textColor': '#2DD4BF', 'fontFamily': 'Segoe UI, Helvetica, Arial, sans-serif'}}}%%
flowchart LR
    M["Euclase Monitor<br/>CPU · GPU · RAM · network"] -- "Corundum ring<br/>shared memory" --> L["Euclase Light<br/>colour follows load"]
    L -- "OpenRGB SDK, loopback" --> H["RGB hardware"]
    M -. "HTTP export, opt-in" .-> E["ESP32 + EuclaseUI<br/>SPI display (example)"]
    A["Adamant SIMD-VIC<br/>LLM inference on CPU"] -- "Corundum ring<br/>tokens" --> V["adamant-view<br/>live dashboard"]
    M -- "Corundum ring<br/>CPU per core, RAM" --> V
```

<p align="center"><img src="assets/divider.png" width="100%" alt=""></p>

<h3 align="center">Engineering approach</h3>

<table>
  <tr>
    <td width="50%" valign="top">
      <b>Tested, and honest about it</b><br>
      <sub>Every repository has automated tests and CI, and a README section on what is verified and what is not, including the parts that could not be run on real hardware.</sub>
    </td>
    <td width="50%" valign="top">
      <b>Verified against references</b><br>
      <sub>Differential testing where it matters (Vajra's decoder against GNU objdump), fault injection at every write, multi-threaded stress tests, ASan / UBSan and TSan where they apply.</sub>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <b>Measured, not guessed</b><br>
      <sub>Benchmarks name the machine, the build and the method, compare against the obvious alternative, and say when a result is noisy.</sub>
    </td>
    <td width="50%" valign="top">
      <b>Private by default</b><br>
      <sub>Tools that watch the machine never send data off it, network services listen on loopback unless told otherwise, downloads are pinned and checksummed, no secrets in repositories.</sub>
    </td>
  </tr>
</table>

<p align="center"><img src="assets/divider.png" width="100%" alt=""></p>

<h3 align="center">Contact</h3>

<p align="center">
  <a href="https://t.me/SIIMUCH"><img src="https://img.shields.io/badge/Telegram-@SIIMUCH-2DD4BF?style=for-the-badge&logo=telegram&logoColor=2DD4BF&labelColor=0F2933" alt="Telegram @SIIMUCH"></a>
  <a href="https://discord.com/users/832983105287618601"><img src="https://img.shields.io/badge/Discord-SIIMUCH-2DD4BF?style=for-the-badge&logo=discord&logoColor=2DD4BF&labelColor=0F2933" alt="Discord SIIMUCH"></a>
  <a href="mailto:semenzamyakin3@gmail.com"><img src="https://img.shields.io/badge/Email-semenzamyakin3%40gmail.com-2DD4BF?style=for-the-badge&logo=gmail&logoColor=2DD4BF&labelColor=0F2933" alt="Email"></a>
</p>

<p align="center">
  <sub>Open to technical co-founder / CTO roles in high-performance and systems-level product teams.</sub>
</p>
