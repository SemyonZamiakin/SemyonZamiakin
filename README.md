# Semyon Zamiakin

Software developer: C, C++, C#, Python, embedded and Linux systems. I build small, dependency-light tools and I document what is tested and what is not.

## Projects

| Project | What it is | Stack | State |
|---|---|---|---|
| [Corundum HFT](https://github.com/SemyonZamiakin/CorundumHFT) | Zero-copy lock-free ring buffer in shared memory for high-frequency telemetry between processes; no syscalls or heap on the hot path; 74 ns one-way vs 6.7 µs for a pipe on Windows | C11, C++17, Linux, Windows | v1.1.0, CI on Linux x86-64 / arm64 and Windows, sanitizers |
| [Euclase Monitor](https://github.com/SemyonZamiakin/EuclaseMonitor) | Tray system monitor for Windows with a skinnable overlay; publishes metrics to local programs over a Corundum shared-memory ring; 1.3 ms per update | C++17, Win32, GDI+ | v1.1.0, unit and end-to-end tests, CI |
| [Euclase Light](https://github.com/SemyonZamiakin/EuclaseLight) | RGB lighting control panel (GPU, RAM, motherboard) on top of OpenRGB; lights can follow system load from Euclase Monitor | C++17 core, WPF (.NET 10) | v1.1.0, 68 core checks, verified on one PC |
| [EuclaseUI](https://github.com/SemyonZamiakin/EuclaseUI) | UI toolkit for SPI TFT displays with dirty-rectangle flushing | C++11, ESP32 / Arduino | v0.1.0, 38 host checks; not yet verified on hardware |

## Engineering approach

- Tests and CI come with the code; the README states what is verified and what is not.
- No secrets in repositories, pinned and checksummed downloads, loopback-only network services by default.
- Small, readable code with documentation that is itself tested.

## Available for

- Automation for small businesses: chat bots for orders and bookings, price parsers, CRM and spreadsheet integrations.
- Technical co-founder / CTO role in product teams that need an engineer.

To discuss work, open an issue in any of the repositories above.
