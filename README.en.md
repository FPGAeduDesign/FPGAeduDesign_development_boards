<div align="center">

# ⚡ FPGAeduDesign Development Boards

### *Empowering Digital Creators Through Open Hardware*

**[🇬🇧 English](README.md)** | **[🇪🇸 Español](README.es.md)**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![HDL](https://img.shields.io/badge/HDL-VHDL%20%7C%20Verilog-orange.svg)](/)
[![Platform](https://img.shields.io/badge/Platform-FPGA-success.svg)](/)
[![Documentation](https://img.shields.io/badge/Docs-Available-brightgreen.svg)](/)

---

### 🎯 About

*Professional-grade FPGA development boards designed for education, prototyping, and experimentation*

</div>

---

### 🔌 Board Lineup

<table>
<tr>
<td width="33%" align="center">

#### 🟢 **Explorer Lite-1k**

*Entry-Level Powerhouse*

Perfect for beginners and classroom environments

**Ideal for:**
- 📚 Learning fundamentals
- 🎓 Educational projects
- 🧪 Quick prototyping

**[📖 Documentation](Explorer-Lite-1k/docs/)** | **[💻 Examples](Explorer-Lite-1k/examples/)** | **[📦 Prebuilt](Explorer-Lite-1k/prebuilt/)**

</td>
<td width="33%" align="center">

#### 🟡 **Explorer Neo-5k**

*Mid-Range Champion*

Balanced performance for intermediate designs

**Ideal for:**
- 🔧 Complex logic designs
- 🎮 Digital systems
- 📡 Interface development

**[📖 Documentation](Explorer-Neo-5k/docs/)** | **[💻 Examples](Explorer-Neo-5k/examples/)** | **[📦 Prebuilt](Explorer-Neo-5k/prebuilt/)**

</td>
<td width="33%" align="center">

#### 🔴 **Explorer Edge-9k**

*Advanced Platform*

High-capacity solution for serious projects

**Ideal for:**
- 💻 SoC development
- 🚀 Advanced DSP
- 🎛️ Professional prototyping

**[📖 Documentation](Explorer-Edge-9k/docs/)** | **[💻 Examples](Explorer-Edge-9k/examples/)** | **[📦 Prebuilt](Explorer-Edge-9k/prebuilt/)**

</td>
</tr>
</table>

---

### 💡 Features

<div align="center">

| Feature | Description |
|:-------:|:------------|
| 🎨 **Dual HDL Support** | Complete examples in both VHDL and Verilog |
| 📦 **Pre-built Binaries** | Ready-to-flash .fs files for instant testing (no compilation needed) |
| 🔍 **Peripheral Testing** | Validation projects for all onboard components |
| 📖 **Educational Focus** | Step-by-step tutorials and well-commented code |
| 🛠️ **Gowin EDA Ready** | All projects include .gpr files for easy import |
| ⚡ **Quick Start** | Flash binaries in seconds or build from source |

</div>

---

### 📂 Repository Structure

```
FPGAeduDesign-Boards/
│
├── 🔷 Explorer-Lite-1k/
│   ├── 📄 docs/                    # Datasheets, user guides, pinouts
│   ├── 🔧 hardware/                # PCB files, schematics, BOM
│   │
│   ├── 💻 examples/                # Full source code examples
│   │   ├── vhdl/
│   │   │   ├── led_blink/
│   │   │   │   ├── src/            # VHDL source files
│   │   │   │   ├── *.gpr           # Gowin project file
│   │   │   │   └── README.md
│   │   │   ├── uart_test/
│   │   │   ├── spi_interface/
│   │   │   └── i2c_scanner/
│   │   │
│   │   └── verilog/
│   │       ├── led_blink/
│   │       │   ├── src/            # Verilog source files
│   │       │   ├── *.gpr           # Gowin project file
│   │       │   └── README.md
│   │       ├── uart_test/
│   │       └── spi_interface/
│   │
│   └── 📦 prebuilt/                # Ready-to-flash binaries
│       ├── led_blink.fs            # Flash bitstream (no source code)
│       ├── uart_test.fs
│       ├── peripheral_demo.fs
│       └── README.md               # Flashing instructions
│
├── 🔶 Explorer-Neo-5k/
│   ├── 📄 docs/
│   ├── 🔧 hardware/
│   ├── 💻 examples/
│   │   ├── vhdl/
│   │   └── verilog/
│   └── 📦 prebuilt/
│
├── 🔺 Explorer-Edge-9k/
│   ├── 📄 docs/
│   ├── 🔧 hardware/
│   ├── 💻 examples/
│   │   ├── vhdl/
│   │   └── verilog/
│   └── 📦 prebuilt/
│
└── 📚 docs/                        # General documentation
    ├── getting_started.md
    ├── gowin_toolchain_setup.md
    ├── how_to_flash.md
    └── faq.md
```

---

### 🚀 Quick Start

**Option 1: Flash Pre-built Binaries (No toolchain required)**

```bash
# Clone the repository
git clone https://github.com/FPGAeduDesign/FPGAeduDesign-Boards.git

# Navigate to your board's prebuilt folder
cd FPGAeduDesign-Boards/Explorer-Neo-5k/prebuilt

# Flash the bitstream using Gowin Programmer
# See docs/how_to_flash.md for detailed instructions
```

**Option 2: Build from Source**

```bash
# Navigate to an example project
cd FPGAeduDesign-Boards/Explorer-Neo-5k/examples/vhdl/led_blink

# Open the Gowin project file
# Double-click the .gpr file or open it with Gowin EDA

# Build and program through Gowin EDA IDE
```

---

### 🎓 Learning Path

```mermaid
graph LR
    A[🌱 Beginner] -->|Explorer Lite-1k| B[📚 Basics]
    B --> C[🔧 Intermediate]
    C -->|Explorer Neo-5k| D[⚡ Advanced]
    D -->|Explorer Edge-9k| E[🚀 Expert]
```

---

### 🤝 Contributing

We welcome contributions! Whether it's:

- 🐛 Bug reports
- 💡 Feature requests  
- 📝 Documentation improvements
- 🔧 New example projects

Check out our [Contributing Guidelines](CONTRIBUTING.md) to get started.

---

### 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

*Feel free to learn, modify, and build upon these designs!*

---

### 📞 Support & Community

- 🌐 **Website**: [fpgaedudesign.com](https://fpgaedudesign.com)
- 💬 **Discord**: [Join our community](https://discord.gg/fpgaedudesign)
- 🐦 **Twitter**: [@FPGAeduDesign](https://twitter.com/fpgaedudesign)
- 📺 **YouTube**: [@FPGAeduDesign](https://youtube.com/@FPGAeduDesign)
- 📘 **Facebook**: [FPGAeduDesign](https://facebook.com/fpgaedudesign)
- 📸 **Instagram**: [@FPGAeduDesign](https://instagram.com/fpgaedudesign)
- 🎥 **Kick**: [FPGAeduDesign](https://kick.com/fpgaedudesign)
- 🎵 **TikTok**: [@FPGAeduDesign](https://tiktok.com/@fpgaedudesign)
- 📧 **Email**: support@fpgaedudesign.com
- 📖 **Wiki**: [Documentation Hub](https://wiki.fpgaedudesign.com)

---

### 👨‍💻 Follow the Creator

- 📘 **Facebook**: [rsgb24](https://facebook.com/rsgb24)
- 🎵 **TikTok**: [@rsgb24](https://tiktok.com/@rsgb24)

---

<div align="center">

**Made with ⚡ by the FPGAeduDesign Team**

⭐ *Star this repo if you find it useful!* ⭐

</div>
