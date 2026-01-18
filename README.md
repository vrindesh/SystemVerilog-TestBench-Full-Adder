# SystemVerilog-TestBench-Full-Adder
https://www.edaplayground.com/x/BPuu

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/b75f4147-7d8c-450a-aa9d-1da79ae03f41" />

**What is DUT?**

DUT means Design Under Test.

It is the actual hardware design written in Verilog or VHDL.

This is the design we want to check and verify.

Before chip fabrication → it is also called DUV (Design Under Verification).

After fabrication → it is commonly called DUT.

~ In short: DUT is the main design we are testing.

** What is a Testbench?**

A testbench is a separate verification code written to test the DUT.

It does not get synthesized.

It creates inputs (stimulus) for the DUT.

It checks whether the DUT output is correct.

~ Think of it as a testing machine for the design.

 **What is an Interface?**

An interface is a bundle of signals connected to the DUT.

Why do we need it?

DUT may have many input and output signals.

Connecting all signals individually is messy and hard to maintain.

Interface groups all signals into one container.

Benefits:

Cleaner code

Easy reuse

Easy maintenance

~ In short: Interface is a common connection point between testbench and DUT.

** What is a Driver?**

The driver sends data to the DUT.

It drives input signals of the DUT.

It uses tasks defined in the interface.

It does not care about timing details.

~ Think of the driver as a person who presses buttons on the DUT.

~ How does the Driver know what to drive?

This is where the Generator comes in.

**What is a Generator?**

The generator creates valid input data.

It generates transactions (data packets).

It sends these transactions to the driver.

The driver converts this data into actual DUT signals.

~ Generator = data creator
~ Driver = data sender

**What is a Transaction?**

A transaction is a data object (class).

It contains all information needed for one operation.

Example: address, data, read/write, etc.

~ Transaction = structured input data

**Why is a Monitor required?**

The monitor watches the DUT outputs.

It observes DUT signals.

Converts output signals into transactions.

Sends these transactions to the scoreboard.

~ Monitor = observer / listener

**What is a Scoreboard?**

The scoreboard checks correctness.

It has a reference model (golden model).

It knows expected output.

It compares:

DUT output

Expected output
