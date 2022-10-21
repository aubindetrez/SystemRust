# SystemRust
Do what we do in SystemC, in Rust. This is just a small toy project, no guarantee. As of today,
very little opensource tools have coverage, formal verification integrated in one solution
(Chisel and Cocotb).

This project is just an exuse to do something I like (Hardware related) in Rust. 

## Dependencies
Install git and cargo (rust toolchain)
```
sudo apt install git

# The rust website recommands to use (be aware of the security risk):
# https://doc.rust-lang.org/cargo/getting-started/installation.html
curl https://sh.rustup.rs -sSf | sh
```

## Getting started

```
git clone https://github.com/aubindetrez/SystemRust.git
cd SystemRust
cargo run
```

## Example

SystemC description:
```c
#include "systemc.h"

SC_MODULE(adder)          // module (class) declaration
{
  sc_in<int> a, b;        // ports
  sc_out<int> sum;

  void do_add()           // process
  {
    sum.write(a.read() + b.read()); //or just sum = a + b
  }

  SC_CTOR(adder)          // constructor
  {
    SC_METHOD(do_add);    // register do_add to kernel
    sensitive << a << b;  // sensitivity list of do_add
  }
};
```

SystemRust equivalent:
```rust
```

## Documentation

### Modules

### Ports

### Signals

### Exports

### Channels

### Interfaces

### Events

### Data types

### Coverage

### Formal Verification

## Other projects
This project can be use as a library to implement a cycle accurate simulator. The idea would be to
convert Hardware description language in SystemRust (like Verilator does).
