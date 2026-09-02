**EXP NO: 30**

**RTOS TASK SCHEDULING**

**AIM:**

To simulate Round-Robin scheduling.

**SOFTWARE REQUIRED:**

Ubuntu/WSL Ubuntu  
g++  
CMake  
SystemC

**PROGRAM:**

```cpp
#include <systemc.h>

SC_MODULE(rtos_scheduler) {
  void task1() {
    while(true)
    {
      cout << "Task1 Running at "
           << sc_time_stamp() << endl;

      wait(1, SC_SEC);
    }
  }

  void task2() {
    while(true)
    {
      cout << "Task2 Running at "
           << sc_time_stamp() << endl;

      wait(1, SC_SEC);
    }
  }

  SC_CTOR(rtos_scheduler)
  {
    SC_THREAD(task1);
    SC_THREAD(task2);
  }
};

int sc_main(int argc, char* argv[]) {
  rtos_scheduler obj("Scheduler");

  sc_start(6, SC_SEC);

  return 0;
}
```

**OUTPUT:**


<img width="917" height="739" alt="image" src="https://github.com/user-attachments/assets/a1c596c5-ebd5-4a9f-a5a8-88c360d8c7a2" />


**RESULT:**

```
Thus the RTOS task scheduling program has been successfully simulated and verified.
```
