# Technical review

**Review scope:** `README.md` and `CODE-1` on the repository's default branch, inspected November 7, 2026.

The following observations come from static inspection. They are not compile, oscilloscope, RF spectrum, functional, or compliance test results.

## Findings

| Area | Finding | Impact |
| --- | --- | --- |
| BLE claim | The ESP8266 does not provide native Bluetooth/BLE; the nRF24L01+ is not a BLE controller. | Calling the project a BLE implementation overstates its capability. |
| Source packaging | The published file is `CODE-1`; the older README mentions `jammer.ino`. | Published instructions do not match the repository contents. |
| Missing header | The source includes `images.h`, but the repository contains no such file. | Image and disclaimer bitmap references cannot be resolved from published files. |
| GPIO documentation | The previous OLED wiring table used D5/D6, also assigned to the SPI clock and input lines. | The wiring instructions are internally inconsistent and require review. |
| RF behaviour | The source requests an nRF24L01+ constant carrier and changes radio channel settings. | There are no measurements showing what devices, if any, are affected; mode labels are not validation. |
| Power and thermal | The earlier README mentions the radio getting extremely hot. | Treat as an electrical/thermal warning, not normal operation; stop and inspect hardware. |
| Provenance | Source includes mixed-language comments and references to assets absent from the repository. | Original authorship and third-party obligations need verification before licensing. |

## Evidence needed for a defensible release

A reproducible, authorised, **non-disruptive** study should supply a complete source tree, dependency versions, a corrected schematic, offline/receive-only test fixtures, and recorded results with conditions and limitations. Any conducted or radiated RF experiment must undergo an appropriate safety and regulatory review before operation.

## Recommended documentation policy

Do not claim Bluetooth interoperability, selective Wi-Fi effects, range, effectiveness, or legal compliance without independently reproducible evidence. Do not publish photographs or dashboards presented as measured results when they are conceptual or simulated. Keep original source modifications separate from this documentary audit.

## Maintainer

[Sai Tanveesh](https://github.com/Saitanveesh) · [LinkedIn](https://www.linkedin.com/in/sai-tanveesh-028881215/)
