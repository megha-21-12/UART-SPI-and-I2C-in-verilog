# UART, SPI and I²C Protocol Implementations in Verilog/SystemVerilog

A collection of communication protocol implementations developed in Verilog/SystemVerilog for FPGA and RTL Design practice. This repository includes complete implementations of UART (16550-inspired), SPI, Daisy-Chain SPI, and I²C Master along with simulation testbenches and waveform verification.

---

## Features

### UART (16550 Inspired)

- UART Transmitter
- UART Receiver
- Baud Rate Generator
- Configurable Word Length (5/6/7/8 bits)
- Even/Odd/Sticky Parity
- FIFO Integration
- Register Interface
- Interrupt Support
- Loopback Verification
- Error Detection
    - Parity Error
    - Frame Error
    - Break Interrupt
    - Overrun Error

---

### FIFO

- Parameterized FIFO
- Full / Empty Detection
- Threshold Trigger
- Overrun Detection
- Underrun Detection
- Configurable Threshold

---

### SPI

- SPI Master
- SPI Slave
- SPI Mode-0 (CPOL = 0, CPHA = 0)
- Configurable Clock Divider
- Full Duplex Communication
- Master-Slave Verification

---

### Daisy Chain SPI

- Multiple Slave Support
- Serial Data Propagation
- Cascaded Shift Register Implementation
- Daisy Chain Verification

---

### Digilent PMOD Interface

- PMOD Peripheral Communication
- SPI-based Interface
- Simulation Verified

---

### I²C Master

- START Condition
- STOP Condition
- ACK/NACK Detection
- Read Operation
- Write Operation
- Clock Generation
- SDA Bidirectional Control

---

# Repository Structure

```
.
├── UART16550
│   ├── UART TX
│   ├── UART RX
│   ├── Baud Generator
│   ├── FIFO
│   ├── Register File
│   ├── Interrupt Logic
│   └── Testbenches
│
├── SPI
│   ├── Master
│   ├── Slave
│   ├── Testbench
│   └── Waveforms
│
├── Daisy Chain SPI
│   ├── Master
│   ├── Slave
│   ├── Multiple Device Communication
│   └── Testbench
│
├── I2C
│   ├── Master
│   ├── Clock Generator
│   ├── FSM
│   └── Testbench
│
└── Images
```

---

# UART Architecture

```
                    +----------------------+
                    | Register Interface   |
                    +----------+-----------+
                               |
               +---------------+---------------+
               |                               |
        +------+-------+               +-------+------+
        | Baud Generator|              | Interrupt Ctrl|
        +------+-------+               +-------+------+
               |                               |
       +-------+------+               +--------+------+
       | UART TX      |               | UART RX       |
       +-------+------+               +--------+------+
               |                               |
         +-----+-----+                   +-----+-----+
         | TX FIFO   |                   | RX FIFO   |
         +-----------+                   +-----------+
```

---

# UART Features

- Programmable Baud Rate
- Programmable Data Length
- Configurable Parity
- FIFO Support
- Register Controlled Configuration
- Interrupt Generation
- Error Detection
- Loopback Verification

---

# SPI State Machine

```
IDLE
  │
  ▼
SEND
  │
  ▼
SAMPLE
  │
  ▼
WAIT
  │
  └────────────► IDLE
```

---

# UART TX FSM

```
IDLE
  │
  ▼
START
  │
  ▼
SEND DATA
  │
  ▼
PARITY
  │
  ▼
STOP
  │
  ▼
IDLE
```

---

# UART RX FSM

```
IDLE
  │
  ▼
START
  │
  ▼
READ DATA
  │
  ▼
PARITY
  │
  ▼
STOP
  │
  ▼
IDLE
```

---

# I²C FSM

```
IDLE
  │
  ▼
START
  │
  ▼
ADDRESS
  │
  ▼
ACK
  │
  ▼
DATA
  │
  ▼
STOP
```

---

# Simulation

The functionality of each protocol has been verified using simulation.

Verified features include:

- UART Transmission
- UART Reception
- FIFO Read/Write
- FIFO Full & Empty Conditions
- Threshold Interrupt
- SPI Data Transfer
- Daisy Chain SPI Communication
- I²C Read/Write Transactions
- Register Configuration
- Baud Rate Update
- Error Detection

---

# Sample Waveforms

The repository includes simulation waveforms demonstrating:

- UART TX
- UART RX
- FIFO Operations
- UART Register Configuration
- SPI Master-Slave Communication
- Daisy Chain SPI
- I²C Transactions

---

# Tools Used

- Vivado 2023.x
- Verilog
- SystemVerilog
- XSIM Simulator

---

# Applications

- FPGA Communication Systems
- UART Controllers
- SPI Peripheral Interfaces
- Sensor Interfaces
- Embedded Systems
- ASIC/RTL Design Practice
- Digital Design Learning

---

# Future Improvements

- I²C Multi-Master Support
- DMA Support for UART
- APB/AHB Wrapper
- UVM Verification Environment
- Functional Coverage
- Assertions (SVA)

---

# Author

**Megha Anil**


Interested in RTL Design, Digital Design and Verification.
