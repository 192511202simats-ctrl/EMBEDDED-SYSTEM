**EXP NO: 24**

**MODELING CLOCK-DRIVEN CONCURRENT PROCESSES USING SC_THREAD AND WAIT() IN SYSTEMC**

**AIM:**

To understand and implement a clock-driven process using sc_clock, SC_THREAD, wait(), event sensitivity (positive edge trigger) in SystemC.

**APPARATUS/SOFTWARE:**

Linux OS / WSL & Ubuntu  
SystemC

**PROGRAM:**

```cpp
#include <systemc.h>

SC_MODULE(ClockExample)
{
  sc_in<bool> clk;

  void process()
  {
    while (true)
    {
      wait();

      std::cout << "Time: " << sc_time_stamp()
                << " - Clock Triggered" << std::endl;
    }
  }

  SC_CTOR(ClockExample)
  {
    SC_THREAD(process);
    sensitive << clk.pos();
  }
};

int sc_main(int argc, char* argv[])
{
  sc_clock clock("clock", 1, SC_NS);

  ClockExample module("module");
  module.clk(clock);

  sc_start(5, SC_NS);

  return 0;
}
```

**STEPS:**

```text
Edit file: nano test_systemc.cpp

Build:
cd build
make

Run:
./test_systemc
```

**OUTPUT:**


<img width="981" height="527" alt="image" src="https://github.com/user-attachments/assets/74a1bff3-d1d4-4647-8909-aa3f6b3d24be" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
