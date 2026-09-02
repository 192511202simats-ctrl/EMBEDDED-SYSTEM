**EXP NO: 29**

**PRIORITY-BASED INTERRUPT HANDLING**

**AIM:**

To model priority-based interrupt servicing.

**SOFTWARE REQUIRED:**

Ubuntu/WSL Ubuntu  
g++  
CMake  
SystemC

**PROGRAM:**

```cpp
#include <systemc.h>

SC_MODULE(priority_interrupt)
{
  sc_event low_int, high_int;

  void low_ISR() {
    while(true) {
      wait(low_int);

      cout << "Low Priority Interrupt at "
           << sc_time_stamp() << endl;

      wait(3, SC_SEC);
    }
  }

  void high_ISR() {
    while(true) {
      wait(high_int);

      cout << "High Priority Interrupt at "
           << sc_time_stamp() << endl;

      wait(1, SC_SEC);
    }
  }

  void generator() {
    wait(1, SC_SEC);

    low_int.notify();

    wait(1, SC_SEC);

    high_int.notify();
  }

  SC_CTOR(priority_interrupt)
  {
    SC_THREAD(low_ISR);
    SC_THREAD(high_ISR);
    SC_THREAD(generator);
  }
};

int sc_main(int argc, char* argv[]) {
  priority_interrupt obj("Priority_INT");

  sc_start(10, SC_SEC);

  return 0;
}
```

**OUTPUT:**


<img width="917" height="641" alt="image" src="https://github.com/user-attachments/assets/ed0d8c65-cb1d-4b69-804d-a899a55afbdb" />


**RESULT:**

```
Thus priority-based interrupt handling has been successfully modeled and verified.
```
