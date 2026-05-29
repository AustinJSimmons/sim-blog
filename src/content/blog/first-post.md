---
title: "Modeling an ALU in SystemC"
description: "Testing cycle-accurate simulation and instruction latency."
pubDate: 2026-05-29
heroImage: "../../assets/blog-placeholder-1.jpg"
summary: "This post is about how we simulate functional components in systemc. We go through how modules are used and a toy example of"
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
