**EXP NO: 25**

**PRODUCER–CONSUMER PROBLEM USING SYSTEMC**

**AIM:**

To implement and simulate Producer–Consumer problem using SystemC.

**SOFTWARE REQUIRED:**

Ubuntu / WSL Linux  
g++ Compiler  
CMake  
SystemC Library

**ALGORITHM:**

1. Start simulation.
2. Create Producer and Consumer modules.
3. Create FIFO channel of fixed size.
4. Connect producer output to FIFO.
5. Connect consumer input to FIFO.
6. Producer writes data into FIFO.
7. Consumer reads data from FIFO.
8. Run simulation fixed duration.
9. Stop simulation.

**PROGRAM:**

```cpp
#include <systemc.h>

// Producer Module
SC_MODULE(Producer)
{
  sc_fifo_out<int> out;

  void produce() {
    for (int i = 1; i <= 5; i++) {
      cout << "Produced: " << i << endl;
      out.write(i);
      wait(1, SC_SEC);
    }
  }

  SC_CTOR(Producer) {
    SC_THREAD(produce);
  }
};

// Consumer Module
SC_MODULE(Consumer)
{
  sc_fifo_in<int> in;

  void consume()
  {
    int value;

    while (true) {
      in.read(value);
      cout << "Consumed: " << value << endl;
      wait(1, SC_SEC);
    }
  }

  SC_CTOR(Consumer) {
    SC_THREAD(consume);
  }
};

int sc_main(int argc, char* argv[]) {
  sc_fifo<int> fifo(5);

  Producer producer("Producer");
  Consumer consumer("Consumer");

  producer.out(fifo);
  consumer.in(fifo);

  sc_start(10, SC_SEC);

  return 0;
}
```

**COMPILATION:**

```text
mkdir build
cd build
cmake ..
make
```

**EXECUTION:**

```text
./producer_consumer
```

**OUTPUT:**


<img width="939" height="655" alt="image" src="https://github.com/user-attachments/assets/ab924d94-e0ee-419b-970c-d34094e913af" />


**RESULT:**

```
Thus the program has been successfully verified and executed.
```
