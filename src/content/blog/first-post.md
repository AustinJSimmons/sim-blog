---
title: "Modeling an ALU in SystemC"
description: "Testing cycle-accurate simulation and instruction latency."
pubDate: 2026-05-29
---

When designing a functional unit, we define the module logic directly in C++.

```cpp
#include <systemc.h>

SC_MODULE(alu) {
    sc_in<int> opA, opB;
    sc_out<int> result;

    void execute() {
        result.write(opA.read() + opB.read());
    }

    SC_CTOR(alu) {
        SC_METHOD(execute);
        sensitive << opA << opB;
    }
};
