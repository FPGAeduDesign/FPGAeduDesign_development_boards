<div align="center">

# 💻 FPGA Design Examples

**[🇬🇧 English](README.md)** | **[🇪🇸 Español](README.es.md)**

</div>

---

This folder contains complete FPGA design examples with full source code in both **VHDL** and **Verilog**. Each project includes all necessary files to build, simulate, and program your board.

## 📂 Folder Structure

```
examples/
├── vhdl/                      # VHDL examples
│   ├── led_blink/
│   ├── uart_echo/
│   ├── button_led/
│   ├── seven_segment/
│   ├── spi_test/
│   ├── i2c_scanner/
│   └── peripheral_demo/
│
└── verilog/                   # Verilog examples
    ├── led_blink/
    ├── uart_echo/
    ├── button_led/
    ├── seven_segment/
    ├── spi_test/
    ├── i2c_scanner/
    └── peripheral_demo/
```

## 🎯 Available Examples

### 🟢 Beginner Level

| Project | Description | Skills Learned |
|---------|-------------|----------------|
| **led_blink** | Blink LEDs at 1Hz | Clock dividers, basic I/O |
| **button_led** | Map buttons to LEDs | Input handling, debouncing |
| **seven_segment** | 7-segment counter | BCD conversion, multiplexing |

### 🟡 Intermediate Level

| Project | Description | Skills Learned |
|---------|-------------|----------------|
| **uart_echo** | UART echo loopback | Serial communication, state machines |
| **spi_test** | SPI flash communication | SPI protocol, timing control |

### 🔴 Advanced Level

| Project | Description | Skills Learned |
|---------|-------------|----------------|
| **i2c_scanner** | Scan I2C bus for devices | I2C protocol, multi-master bus |
| **peripheral_demo** | Complete system integration | System design, resource management |

## 🚀 How to Use

### 1. Choose Your HDL

Pick either **VHDL** or **Verilog** based on your preference or learning goals:

```bash
# For VHDL
cd vhdl/led_blink

# For Verilog
cd verilog/led_blink
```

### 2. Open in Gowin EDA

Each project folder contains a `.gpr` project file:

1. Launch **Gowin EDA**
2. Click **File → Open** or press `Ctrl+O`
3. Navigate to the project folder
4. Select the `.gpr` file
5. The project will open with all sources configured

### 3. Build the Project

**Using the GUI:**
1. Click **Process → Synthesize** (or press `F11`)
2. Click **Process → Place & Route** (or press `F9`)
3. Click **Process → Generate Bitstream** (or press `F5`)

**Using the TCL Console:**
```tcl
run all
```

### 4. Program Your Board

1. Connect your board via USB
2. Click **Tools → Programmer** (or press `Ctrl+Alt+F`)
3. Click **Scan Device**
4. Select your FPGA from the list
5. The bitstream should already be loaded
6. Click **Program/Configure**

## 📋 Project Contents

Each example project includes:

```
project_name/
├── README.md              # Project-specific documentation
├── project_name.gpr       # Gowin project file
├── src/
│   ├── top.vhd/.v        # Top-level design file
│   ├── module1.vhd/.v    # Additional design files
│   └── module2.vhd/.v
├── constraints/
│   └── board.cst         # Pin constraints and timing
├── sim/
│   └── testbench.vhd/.v  # Simulation testbench (if available)
└── docs/
    ├── schematic.png     # Block diagram
    └── timing.png        # Timing diagram (if applicable)
```

## 🎓 Learning Path

### For Beginners

1. **Start with:** `led_blink`
   - Understand clock signals
   - Learn basic I/O
   - Get familiar with Gowin EDA workflow

2. **Then try:** `button_led`
   - Add input handling
   - Learn about debouncing
   - Understand combinational vs sequential logic

3. **Next step:** `seven_segment`
   - Work with BCD encoding
   - Learn multiplexing techniques
   - Create more complex output patterns

### For Intermediate Users

4. **Move to:** `uart_echo`
   - Implement state machines
   - Handle serial communication
   - Work with protocols

5. **Continue with:** `spi_test`
   - Master synchronous serial protocols
   - Interface with real hardware (flash memory)
   - Handle timing requirements

### For Advanced Users

6. **Challenge yourself:** `i2c_scanner`
   - Implement bidirectional protocols
   - Handle multi-master scenarios
   - Debug complex timing issues

7. **Complete with:** `peripheral_demo`
   - Integrate multiple subsystems
   - Manage resources efficiently
   - Create complete FPGA systems

## 🔧 Customization Guide

### Changing Clock Frequency

Most designs use a clock divider. To modify the blink rate or timing:

**VHDL:**
```vhdl
-- Original: 1Hz blink (50MHz / 50000000 = 1Hz)
constant DIVIDER : integer := 50000000;

-- Modified: 2Hz blink
constant DIVIDER : integer := 25000000;
```

**Verilog:**
```verilog
// Original: 1Hz blink
parameter DIVIDER = 50000000;

// Modified: 2Hz blink
parameter DIVIDER = 25000000;
```

### Adapting to Different Boards

If you're using a different board from this series:

1. **Update pin constraints** in `constraints/board.cst`
2. **Verify clock frequency** matches your board's oscillator
3. **Check I/O voltage** levels in constraints
4. **Adjust peripheral addresses** if using different hardware

### Adding Your Own Features

1. Create a new branch: `git checkout -b my-feature`
2. Modify the source files
3. Test thoroughly
4. Document your changes
5. Consider contributing back! (See [CONTRIBUTING.md](../CONTRIBUTING.md))

## 📊 Simulation

Some projects include testbenches for simulation:

### Using Gowin EDA Simulator

1. Open the project in Gowin EDA
2. Click **Tools → Simulator**
3. Add testbench files if not already included
4. Click **Run Simulation**
5. View waveforms in the integrated viewer

### Using ModelSim/QuestaSim

```bash
# Compile VHDL
vcom -work work src/*.vhd
vcom -work work sim/testbench.vhd

# Run simulation
vsim -do "run -all" work.testbench

# For Verilog
vlog -work work src/*.v
vlog -work work sim/testbench.v
vsim -do "run -all" work.testbench
```

### Using GHDL (VHDL only, open source)

```bash
# Analyze files
ghdl -a src/*.vhd
ghdl -a sim/testbench.vhd

# Elaborate
ghdl -e testbench

# Run
ghdl -r testbench --wave=output.ghw

# View with GTKWave
gtkwave output.ghw
```

## 💡 Tips & Best Practices

### Code Organization
- ✅ Keep modules small and focused
- ✅ Use meaningful signal names
- ✅ Comment complex logic
- ✅ Follow consistent naming conventions

### Timing
- ✅ Always synchronize external inputs
- ✅ Avoid combinational loops
- ✅ Meet timing constraints
- ✅ Use synchronous resets when possible

### Debugging
- ✅ Start simple, add complexity gradually
- ✅ Use LEDs for quick status indication
- ✅ Implement UART debug output
- ✅ Simulate before synthesizing

### Resource Usage
- ✅ Check resource utilization reports
- ✅ Optimize critical paths
- ✅ Use block RAM efficiently
- ✅ Consider power consumption

## 🐛 Common Issues

### Synthesis Errors

**Problem:** "Signal not declared"
- **Solution:** Check spelling and scope of signal declarations

**Problem:** "Multiple drivers"
- **Solution:** Ensure signals are only driven from one process/always block

**Problem:** "Type mismatch"
- **Solution:** Verify data types match in assignments

### Timing Issues

**Problem:** Design doesn't meet timing
- **Solution:** Add pipeline stages, reduce logic depth, or lower clock frequency

**Problem:** Metastability warnings
- **Solution:** Add synchronizer flip-flops for asynchronous inputs

### Hardware Issues

**Problem:** Design doesn't work on hardware but simulates fine
- **Solution:** Check constraints file, verify I/O standards, add reset logic

**Problem:** Intermittent behavior
- **Solution:** Check for uninitialized signals, add proper resets

## 📚 Additional Resources

- 📖 [Gowin EDA User Guide](https://www.gowinsemi.com/en/support/database/)
- 📘 [VHDL Reference](https://www.ics.uci.edu/~jmoorkan/vhdlref/)
- 📗 [Verilog Reference](https://www.asic-world.com/verilog/index.html)
- 🎥 [Video Tutorials](https://youtube.com/@FPGAeduDesign)
- 💬 [Community Discord](https://discord.gg/fpgaedudesign)

## 🤝 Contributing

Found a bug or want to improve an example?

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/amazing-example`
3. Commit your changes: `git commit -m 'Add amazing example'`
4. Push to the branch: `git push origin feature/amazing-example`
5. Open a Pull Request

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for detailed guidelines.

## 📞 Need Help?

- 🐛 **Found a bug?** Open an [issue](https://github.com/FPGAeduDesign/FPGAeduDesign-Boards/issues)
- 💬 **Have questions?** Join our [Discord](https://discord.gg/fpgaedudesign)
- 📧 **Email support:** support@fpgaedudesign.com
- 📖 **Documentation:** Check the [Wiki](https://wiki.fpgaedudesign.com)

---

<div align="center">

**Happy coding!** 🚀 **Don't forget to check the [prebuilt folder](../prebuilt/) for ready-to-flash binaries!**

</div>
