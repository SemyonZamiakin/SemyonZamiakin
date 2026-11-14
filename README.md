# Semyon Zamiakin

Software developer working close to the machine: C, C++, C#, Python, Windows and Linux internals, shared memory, binary code, embedded. I build [Euclase](https://github.com/SemyonZamiakin), a software studio for systems-level tools, and I document what is tested and what is not.

## Projects

| Project | What it is | Stack | State |
|---|---|---|---|
| [Vajra Binary Core](https://github.com/SemyonZamiakin/VajraBinaryCore) | Live patching for running C++ programs: swaps machine code and migrates live objects to new struct layouts, with pointers fixed up, in one atomic, revertible transaction; own x86-64 decoder, matches objdump on 2M+ instructions | C++17, x86-64 Linux, Windows | v0.1.0, 75 tests, CI on Linux (incl. ASan/UBSan/TSan) and Windows |
| [Corundum HFT](https://github.com/SemyonZamiakin/CorundumHFT) | Zero-copy lock-free ring buffer in shared memory for high-frequency telemetry between processes; no syscalls or heap on the hot path; 74 ns one-way vs 6.7 µs for a pipe on Windows | C11, C++17, Linux, Windows | v1.1.0, CI on Linux x86-64 / arm64 and Windows, sanitizers |
| [Euclase SessionGuard](https://github.com/SemyonZamiakin/EuclaseSessionGuard) | Local, tamper-evident audit of messengers and social-network sessions on your own computer: when each client ran, used the network, had focus, and who touched its session files; HMAC-chained log, no network access at all | Python 3.11+, no dependencies, Windows, Linux | v0.2.0, 129 tests, CI on Windows, Linux, macOS; Windows file-audit mode not yet run live |
| [Euclase Monitor](https://github.com/SemyonZamiakin/EuclaseMonitor) | Tray system monitor for Windows with a skinnable overlay; publishes metrics to local programs over a Corundum shared-memory ring; 1.3 ms per update | C++17, Win32, GDI+ | v1.1.0, unit and end-to-end tests, CI |
| [Euclase Light](https://github.com/SemyonZamiakin/EuclaseLight) | RGB lighting control panel (GPU, RAM, motherboard) on top of OpenRGB; lights can follow system load from Euclase Monitor | C++17 core, WPF (.NET 10) | v1.1.0, 68 core checks, verified on one PC |
| [EuclaseUI](https://github.com/SemyonZamiakin/EuclaseUI) | UI toolkit for SPI TFT displays with dirty-rectangle flushing | C++11, ESP32 / Arduino | v0.1.0, 38 host checks; not yet verified on hardware |

The projects build on each other: Euclase Monitor publishes its metrics over Corundum HFT, and Euclase Light reads them to drive RGB lighting.

## Engineering approach

- Tests and CI come with the code, and every README has a section on what is verified and what is not, including the parts I could not run on real hardware.
- Verification goes past unit tests where it matters: differential testing against reference tools (Vajra's decoder against GNU objdump), fault injection at every write, multi-threaded stress tests, sanitizers, tamper tests for logs.
- Measured numbers only: benchmarks state the machine, the build and the method, and say when a result is noisy.
- No secrets in repositories, pinned and checksummed downloads, loopback-only network services by default, and tools that watch the machine never send data off it.
- Documentation that is itself tested where possible (every example in the Euclase Monitor customization guide is loaded by its test suite).

## Available for

- Systems and low-level work: native tooling for Windows and Linux, IPC and performance, binary instrumentation, security and audit tools, embedded.
- Business automation: chat bots for orders and bookings, price parsers, CRM, 1C and spreadsheet integrations.
- Technical co-founder / CTO role in product teams that need an engineer.

To discuss work, open an issue in any of the repositories above.
