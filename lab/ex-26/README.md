**EXP NO: 26**

**TRANSACTION LEVEL MODELING (TLM) USING SYSTEMC**

**AIM:**

To model and simulate a simple Transaction-Level Model (TLM) using Initiator and Target modules in SystemC.

**SOFTWARE REQUIRED:**

Ubuntu/WSL Ubuntu  
g++  
CMake  
SystemC with TLM-2.0 library

**PROGRAM:**

```cpp
#include <systemc>
#include <tlm>
#include <tlm_utils/simple_initiator_socket.h>
#include <tlm_utils/simple_target_socket.h>

using namespace sc_core;
using namespace tlm;
using namespace std;

// Target
struct Target : sc_module {
  tlm_utils::simple_target_socket<Target> socket;

  SC_CTOR(Target) : socket("socket") {
    socket.register_b_transport(this, &Target::b_transport);
  }

  void b_transport(tlm_generic_payload& trans, sc_time& delay) {
    int* data = (int*) trans.get_data_ptr();

    cout << "Target received: " << *data << endl;

    delay += sc_time(10, SC_NS);
  }
};

// Initiator
struct Initiator : sc_module {
  tlm_utils::simple_initiator_socket<Initiator> socket;

  SC_CTOR(Initiator) : socket("socket") {
    SC_THREAD(thread_process);
  }

  void thread_process() {
    tlm_generic_payload trans;
    sc_time delay = SC_ZERO_TIME;

    int data = 555;

    trans.set_data_ptr(
      reinterpret_cast<unsigned char*>(&data)
    );

    trans.set_data_length(sizeof(data));

    cout << "Initiator sending: " << data << endl;

    socket->b_transport(trans, delay);

    wait(delay);
  }
};

int sc_main(int argc, char* argv[]) {
  Initiator initiator("initiator");
  Target target("target");

  initiator.socket.bind(target.socket);

  sc_start();

  return 0;
}
```

**COMPILATION:**

```text
cd ~/systemc_test
mkdir build
cd build
cmake ..
make
```

**EXECUTION:**

```text
./tlm
```

**OUTPUT:**

<img width="947" height="617" alt="image" src="https://github.com/user-attachments/assets/9c42ee72-3019-46a1-bf66-a605188c0c59" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
