# Leningrad2-Upgrade-Kit

## Memory Expansions and AY/TS for Leningrad-2.  
  
> [English](README.en.md) | [Русский](README.md)  
  
This repository contains hardware expansion board projects designed for the RAM and sound upgrade of the "Leningrad-2" home computer. 

These modules allow you to upgrade the stock 48K base model to a full **128KB** or **256KB** system. This expansion is essential for running modern homebrew games, advanced demos, and heavy software. 

The boards are designed with a primary goal: minimizing messy wire-wrap modifications ("spaghetti wiring"). They connect directly to the system expansion slot, transforming the basic Leningrad-2 48K into a powerhouse 128K+ class machine.

***

## 🎸 All-in-One Module Features

*   **Memory:** Upgrade to 128KB (Standard Spectrum 128 mapping) or 256KB using classic DRAM chips.
*   **Sound:** Integrated AY-3-8910 sound chip (or YM2149F equivalent).
*   **Turbo Sound (Optional):** Supports dual AY/YM chips to achieve full 6-channel Turbo Sound capabilities.
*   **Beep Mixer:** The standard motherboard Beeper signal is mixed directly into the main audio channel output.
*   **Circuitry:** Standard port decoding logic (`#7FFD` for memory paging and `#BFFD`/`#FFFD` for sound chip registers).
*   **Compatibility:** Full support for games and demos requiring official memory bank switching.

***

## 🧩 Hardware Construction & Connection (Bus Through-Port)

The upgrade boards feature a **Bus Through-port** design. They plug directly into the main system connector of the Leningrad-2, while providing an identical expansion slot connector on top.

*   **Plug-and-Play:** This allows you to stack other peripherals—like BDI (TR-DOS) or DivMMC controllers—directly on top of this expansion board without using flat ribbon cables.
*   **Motherboard Integration:** Optimized for seamless operation with my custom version of the Leningrad-2-48k. 
*   **Universal Compatibility:** The board can also be wired to any standard vintage or third-party version of the Leningrad-2. In this case, you will only need to manually route a few core control signals according to the provided schematic.

***

## 📦 Modular RAM Replacement (RAM Plug-in Board)

As an alternative to chip stacking ("piggybacking"), this project includes a specialized adapter PCB that holds 16x KR565RU5 (КР565РУ5 / 4164) DRAM chips to replace the stock computer memory.

*   **Installation:** The adapter plugs directly into the original RAM IC sockets (or footprints) on the Leningrad-2 motherboard.
*   **Universal Fit:** The pin group layout completely matches the original RU5 memory chip placement found across all known Leningrad-2 PCB revisions.
*   **Key Advantage:** No messy chip stacking. It provides a clean install, a reliable contact interface, and superior cooling/ventilation for the RAM chips.
*   **Solderless Upgrade:** Equipped with thin male pin headers (PLS-type) that slide perfectly into standard round-hole machined IC sockets on the mainboard. It preserves the clean, aesthetics and long-term hardware reliability.

---

## 🛠️ Project Modules

### 1. Leningrad 2 Expansion 128k & AY-3-8910 (YM2149F)
*   [Schematics](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Placement](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Gerber Files](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit)

### 2. Leningrad 2 Expansion 128k & Turbo Sound 2x YM2149F (AY-3-8910)
*   [Schematics](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Placement](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Gerber Files](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit)

### 3. Leningrad 2 Expansion 256k & Turbo Sound 2x YM2149F (AY-3-8910)
*   [Schematics](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Placement](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Gerber Files](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit)

### 4. RAM Plug-in Board 2x64
*   [Schematics](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Placement](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit) | [Gerber Files](https://github.com/Alex-2-Graf/Leningrad2-Upgrade-Kit)

---

## 🔧 Mainboard Preparation

*   **For my custom Leningrad-2-48k revision:** Preparation is as simple as configuring the onboard jumpers **JP5 to JP11** (clearly labeled on the PCB silkscreen).
*   **For stock/vintage motherboards:** Please consult the descriptive documentation and schematics provided in this repository to properly tap the missing address lines.

---

## 💾 Memory Testing Software

To verify your new memory configuration, you can use the following diagnostic tools included in the repository:
*   **GTEST**
*   **HFT**
