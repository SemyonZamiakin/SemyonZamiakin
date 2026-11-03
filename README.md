# Semyon Zamiakin

Software developer: C++, C#, Python, embedded. I build small, dependency-light tools and I document what is tested and what is not.

## Projects

| Project | What it is | Stack | State |
|---|---|---|---|
| [Quasar Monitor](https://github.com/SemyonZamiakin/QuasarMonitor) | Tray system monitor for Windows with a skinnable overlay, about 5 MB of RAM, local JSON metrics export | C++17, Win32, GDI+ | v0.1.0, 115 automated checks, CI |
| [Quasar Light](https://github.com/SemyonZamiakin/QuasarLight) | RGB lighting control panel (GPU, RAM, motherboard) on top of OpenRGB | C++17 core, WPF (.NET 10) | v0.1.0, 46 core checks, verified on one PC |
| [QuasarUI](https://github.com/SemyonZamiakin/QuasarUI) | UI toolkit for SPI TFT displays with dirty-rectangle flushing | C++11, ESP32 / Arduino | v0.1.0, 38 host checks; not yet verified on hardware |

## Engineering approach

- Tests and CI come with the code; the README states what is verified and what is not.
- No secrets in repositories, pinned and checksummed downloads, loopback-only network services by default.
- Small, readable code with documentation that is itself tested.

## Available for

- Automation for small businesses: chat bots for orders and bookings, price parsers, CRM and spreadsheet integrations.
- Technical co-founder / CTO role in product teams that need an engineer.

To discuss work, open an issue in any of the repositories above.
