**EXP NO: 28**

**COUNTING SEMAPHORE IN SYSTEMC**

**AIM:**

To implement Counting Semaphore allowing multiple resource access.

**SOFTWARE REQUIRED:**

Ubuntu/WSL Ubuntu  
g++  
CMake  
SystemC

**PROGRAM:**

```cpp
#include <systemc.h>

SC_MODULE(counting_semaphore)
{
  int sem;

  void task() {
    while(true)
    {
      wait(1, SC_SEC);

      if(sem > 0)
      {
        sem--;

        cout << "Task Accessing Resource at "
             << sc_time_stamp()
             << " Remaining: " << sem << endl;

        wait(2, SC_SEC);

        sem++;
      }
    }
  }

  SC_CTOR(counting_semaphore)
  {
    sem = 2;

    SC_THREAD(task);
    SC_THREAD(task);
    SC_THREAD(task);
  }
};

int sc_main(int argc, char* argv[]) {
  counting_semaphore obj("Counting");

  sc_start(10, SC_SEC);

  return 0;
}
```

**OUTPUT:**


<img width="933" height="659" alt="image" src="https://github.com/user-attachments/assets/6e37385b-52a8-424f-84db-794b0c2bb260" />


**RESULT:**

```
Thus the counting semaphore has been successfully implemented and verified.
```
