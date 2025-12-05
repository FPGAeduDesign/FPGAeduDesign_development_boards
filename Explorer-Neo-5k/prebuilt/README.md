<div align="center">

# 📦 Pre-built Bitstreams

**[🇬🇧 English](README.md)** | **[🇪🇸 Español](README.es.md)**

</div>

---

This folder contains ready-to-flash `.fs` bitstream files for quick testing of your FPGA board without needing to install any synthesis tools.

## 🎯 What's Inside

These pre-compiled binaries allow you to test all the peripherals on your board instantly:

| File | Description | Peripherals Tested |
|------|-------------|-------------------|
| `led_blink.fs` | Classic LED blinker | LEDs |
| `uart_echo.fs` | UART loopback test | UART, LEDs |
| `button_led.fs` | Button to LED mapping | Buttons, LEDs |
| `seven_segment.fs` | 7-segment display counter | 7-segment display |
| `spi_test.fs` | SPI flash communication | SPI Flash, LEDs |
| `i2c_scanner.fs` | I2C device scanner | I2C bus, UART |
| `peripheral_demo.fs` | Complete peripheral showcase | All onboard peripherals |

## 🚀 How to Flash

### Method 1: Using Gowin Programmer (Recommended)

#### Windows / Linux / macOS

1. **Download Gowin Programmer**
   - Visit: https://www.gowinsemi.com/en/support/download_eda/
   - Download "Gowin Programmer" (standalone tool, no full IDE needed)
   - Install and launch the application

2. **Connect Your Board**
   - Connect your FPGA board via USB
   - Power on the board
   - Wait for drivers to install (Windows)

3. **Configure the Programmer**
   - Open Gowin Programmer
   - Click **"Scan Device"** or press `Ctrl+D`
   - Your FPGA should appear in the device list
   
4. **Load the Bitstream**
   - Right-click on the detected device
   - Select **"Add File"**
   - Browse to the `.fs` file you want to flash
   - Set **Operation** to: `embFlash Erase, Program thru GAO-Bridge`
   
5. **Program the Device**
   - Click the **"Program/Configure"** button (or press `Ctrl+P`)
   - Wait for "Program done" message
   - Your board should now be running the design!

### Method 2: Using OpenFPGALoader (Open Source)

#### Installation

```bash
# Ubuntu/Debian
sudo apt install openfpgaloader

# macOS (with Homebrew)
brew install openfpgaloader

# Or build from source
git clone https://github.com/trabucayre/openFPGALoader.git
cd openFPGALoader
mkdir build && cd build
cmake ..
make
sudo make install
```

#### Flashing

```bash
# Flash to SRAM (temporary - lost on power cycle)
openFPGALoader -b YOUR_BOARD led_blink.fs

# Flash to embedded Flash (persistent)
openFPGALoader -b YOUR_BOARD -f led_blink.fs

# List supported boards
openFPGALoader --list-boards
```

## 🔧 Troubleshooting

### Device Not Detected

**Windows:**
- Install Gowin USB drivers from the Gowin Programmer installation folder
- Check Device Manager for "Unknown Device" and update drivers manually
- Try a different USB cable (must support data, not just power)

**Linux:**
- Add udev rules for USB access:
  ```bash
  sudo nano /etc/udev/rules.d/90-gowin.rules
  ```
  Add:
  ```
  SUBSYSTEM=="usb", ATTR{idVendor}=="0547", ATTR{idProduct}=="1002", MODE="0666"
  ```
  Then reload:
  ```bash
  sudo udevadm control --reload-rules
  sudo udevadm trigger
  ```

**macOS:**
- Grant USB access permissions when prompted
- Try unplugging/replugging the board

### Programming Failed

- Ensure the board is properly powered
- Try a different USB port (use USB 2.0 ports if USB 3.0 fails)
- Check that jumpers are in the correct position (see board documentation)
- Verify the `.fs` file is compatible with your specific board model

### Board Not Working After Flash

- Some designs require external connections (e.g., UART needs USB-Serial adapter)
- Check the design description above for required peripherals
- Power cycle the board
- Try reflashing the bitstream

## 📖 Design Descriptions

### `led_blink.fs`
- **What it does**: Blinks all onboard LEDs in sequence
- **Requirements**: None - works standalone
- **Expected behavior**: LEDs blink at ~1Hz
- **Use case**: Verify board is working and clock is running

### `uart_echo.fs`
- **What it does**: Echoes back any character received on UART
- **Requirements**: USB-to-Serial adapter connected to UART pins
- **Settings**: 115200 baud, 8N1
- **Expected behavior**: Type in terminal, see characters echoed back
- **Use case**: Test UART communication

### `button_led.fs`
- **What it does**: Each button controls a corresponding LED
- **Requirements**: None - works standalone
- **Expected behavior**: Press button → LED turns on
- **Use case**: Test button inputs and LED outputs

### `seven_segment.fs`
- **What it does**: Counts 0-9 on 7-segment display
- **Requirements**: None - works standalone
- **Expected behavior**: Display counts up every second
- **Use case**: Test 7-segment display driver

### `spi_test.fs`
- **What it does**: Reads SPI flash ID and blinks LED pattern
- **Requirements**: None - uses onboard SPI flash
- **Expected behavior**: LED pattern indicates flash detected
- **Use case**: Verify SPI flash communication

### `i2c_scanner.fs`
- **What it does**: Scans I2C bus and reports devices via UART
- **Requirements**: USB-to-Serial adapter, optional I2C devices
- **Settings**: 115200 baud, 8N1
- **Expected behavior**: Terminal shows detected I2C addresses
- **Use case**: Test I2C bus and detect connected devices

### `peripheral_demo.fs`
- **What it does**: Comprehensive test of all board features
- **Requirements**: USB-to-Serial adapter for status messages
- **Settings**: 115200 baud, 8N1
- **Expected behavior**: Interactive demo controlled via UART
- **Use case**: Complete board validation

## 💡 Tips

- **First time?** Start with `led_blink.fs` to verify everything works
- **Need source code?** Check the `../examples/` folder for full projects
- **Want to modify?** Open the corresponding `.gpr` project file in Gowin EDA
- **Multiple boards?** Flash different designs to compare functionality
- **Persistent storage**: Flashing to embedded Flash survives power cycles

## 📞 Need Help?

- 📖 Check the main [README](../../README.md) for support channels
- 🐛 Found an issue? Open a GitHub issue
- 💬 Join our Discord for community support
- 📧 Email: support@fpgaedudesign.com

---

<div align="center">

**Ready to dive deeper?** Check out the [examples folder](../examples/) for full source code! 🚀

</div>
