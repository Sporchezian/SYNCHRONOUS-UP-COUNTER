### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.
   
3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**

SYNCHRONOUS-UP-COUNTER

```
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```
SYNCHRONOUS-DOWN-COUNTER

```
module ex12(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out-1;
end
endmodule
```
Developed by: PORCHEZIAN S

RegisterNumber:25017994

**RTL LOGIC UP COUNTER**

SYNCHRONOUS-UP-COUNTER:

<img width="1600" height="863" alt="Screenshot 2025-12-10 111103" src="https://github.com/user-attachments/assets/3e243bc3-85c8-4a74-8834-22bda8ba559d" />

SYNCHRONOUS-DOWN-COUNTER:

<img width="1638" height="857" alt="Screenshot 2025-12-10 113430" src="https://github.com/user-attachments/assets/425460b2-00ac-46e0-b03f-a15e2efcf834" />

**TIMING DIAGRAM FOR IP COUNTER**

SYNCHRONOUS-UP-COUNTER:

<img width="1918" height="167" alt="Screenshot 2025-12-10 111425" src="https://github.com/user-attachments/assets/c0f5bb9c-0d53-435d-b82b-e650449a365a" />

SYNCHRONOUS-DOWN-COUNTER:

<img width="1919" height="174" alt="Screenshot 2025-12-10 113613" src="https://github.com/user-attachments/assets/4c3b32a4-f463-44a0-8600-6b1aa129c1e5" />

**TRUTH TABLE**

![WhatsApp Image 2025-12-10 at 11 22 58_ab0bde01](https://github.com/user-attachments/assets/515b790c-8146-4a09-9992-6a4f536e5b9a)


**RESULTS**

Thus to implement 4 bit synchronous up counter and down counter and validate functionality has been implemented successfully.
