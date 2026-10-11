# LEVEL 1 REPORT
# Electronic Design

>## TASK 2: Blue Pill Reloaded

`Objective:`

 To design and develop a custom STM32 Blue Pill-inspired PCB using Altium Designer. Integrating enhanced features, configuring the microcontroller using STM32CubeMX.

![3d view](https://raw.githubusercontent.com/LakshithaV419/Images/main/3d%20view.png)

`Theory:`

The STM32 Blue Pill Reloaded is a custom microcontroller development board designed with enhanced features such as USB Type-C connectivity, onboard motion and environmental sensors, an addressable RGB LED, and dedicated expansion headers. The board is designed to provide a flexible platform for embedded systems development, sensor interfacing, and prototyping.

![schematic](https://raw.githubusercontent.com/LakshithaV419/Images/main/schematic1u.png)

![schematic](https://raw.githubusercontent.com/LakshithaV419/Images/main/schematic2.png)

#### 1. Power Supply Module

The power supply module provides the regulated voltage required for the operation of the microcontroller and peripheral components. An AP2112K-3.3 low-dropout (LDO) voltage regulator is used to convert the input supply voltage to a stable 3.3 V output. This regulated voltage powers the STM32 microcontroller and other compatible components on the board. The module includes input and output filtering capacitors to improve supply stability and reduce voltage fluctuations. 

#### 2. STM32 Microcontroller Unit (MCU)

The STM32 microcontroller acts as the central processing unit of the board. It executes the firmware, processes sensor data, controls the status indicator, and manages communication with external devices. It has general-purpose input/output (GPIO) pins and interfaces such as UART, SPI, and I²C, enabling communication with sensors and external modules. Reset and boot configuration circuitry supports reliable startup and restarting of the system. An external clock circuit provides the clock reference required for timing-sensitive operations and accurate system operation.

#### 3. USB Type-C Interface

The USB Type-C interface provides a modern and convenient connector for supplying power and supporting USB communication. It improves usability by allowing the board to connect to compatible USB power sources and host devices.

#### 4. Reset and Boot Configuration Module

The reset circuit allows the microcontroller to restart when required. It helps recover the system from unexpected states and facilitates repeated testing during firmware development. The associated filtering components help reduce the effects of electrical noise on the reset signal.

The boot configuration circuitry determines the startup mode of the microcontroller. It allows the device to start executing the user application from internal flash memory or enter a supported system bootloader mode, depending on the selected configuration.

#### 5. Clock Circuit

The clock circuit provides timing references for the microcontroller. A high-speed crystal oscillator can serve as the reference for the system clock, enabling accurate execution of instructions and peripheral operations. A low-speed crystal, when implemented, can provide a precise reference for the real-time clock (RTC) and timekeeping functions. The associated load capacitors help the crystals operate within their specified frequency and stability requirements.

#### 6. Inertial Measurement Unit (IMU)

The MPU6050 is a six-axis inertial measurement unit that integrates a three-axis accelerometer and a three-axis gyroscope. The accelerometer measures linear acceleration along three perpendicular axes, while the gyroscope measures angular velocity around these axes. The sensor is useful for motion detection, tilt estimation, orientation tracking, vibration analysis, and gesture recognition. The collected measurements can be processed by the microcontroller to determine the movement and orientation of an object.

#### 7. Environmental Sensor Module

The BME280 is an environmental sensor capable of measuring temperature, relative humidity, and atmospheric pressure. It provides environmental data that can be used in weather monitoring, indoor environmental sensing, and other measurement applications. The microcontroller reads the sensor measurements and can process, store, or transmit them to an external system. The sensor's compact size and low power consumption make it suitable for embedded applications.

#### 8. RGB Status Indicator

The WS2812B is an addressable RGB LED that integrates red, green, and blue LED elements with an internal control circuit. It can generate a wide range of colours and brightness levels using a digital data signal from the microcontroller. The LED provides visual feedback about the operating state of the board. For example, different colours can be assigned to indicate normal operation, warnings, communication activity, or system faults. A series resistor and a decoupling capacitor support reliable signal and power operation.

#### 9. UART Debug Header

The UART debug header provides a serial communication interface for debugging and testing. It allows the microcontroller to exchange data with a computer, USB-to-UART adapter, or another compatible device. UART communication is useful for transmitting diagnostic messages, monitoring program execution, receiving commands, and troubleshooting firmware. It is particularly valuable during the development and testing stages of embedded systems.

#### 10. SPI Expansion Header

The Serial Peripheral Interface (SPI) expansion header allows external SPI-compatible devices to be connected to the board. SPI is a synchronous serial communication protocol commonly used for high-speed data transfer between a microcontroller and peripheral devices.
The interface can support devices such as external memory, displays, data converters, and compatible sensors. The expansion header increases the flexibility of the board by allowing additional hardware to be integrated without modifying the main circuit.

#### 11. I²C Expansion Header

The Inter-Integrated Circuit (I²C) expansion header provides an interface for connecting external I²C-compatible devices. I²C uses a shared two-wire communication bus and supports communication with multiple devices using their assigned addresses.It is commonly used with sensors, real-time clocks, GPIO expanders, and other low-speed peripherals. The expansion header allows additional modules to be integrated while reducing the number of microcontroller pins required.

#### 12. GPIO and Peripheral Expansion Headers

The general-purpose input/output (GPIO) expansion headers expose selected microcontroller pins for external use. These pins can be configured as digital inputs, digital outputs, or alternate-function pins for supported peripherals. The headers allow users to connect external circuits, switches, LEDs, sensors, and other modules. They make the board suitable for rapid prototyping, experimentation, and educational embedded systems projects.

#### 13. Decoupling Capacitors

Decoupling capacitors are essential components used to maintain a stable power supply for integrated circuits. They help suppress high-frequency noise, reduce transient voltage variations, and provide short bursts of current when a component's demand changes rapidly.

Small ceramic capacitors, typically around 100 nF, are commonly used for high-frequency decoupling near the power pins of the microcontroller and sensors. Larger capacitors, such as 10 µF, help manage lower-frequency supply variations and sudden changes in current demand. The exact values depend on the requirements of the components and the power-supply design.

In this board, decoupling capacitors are included in the power supply, microcontroller, sensor, and RGB LED sections. Their effectiveness depends on suitable component selection and placement close to the relevant power pins, with short connections to the ground return path.

#### 14. LED Indicator Circuit

The board also includes conventional LED indicator circuitry for providing visual information about power or circuit operation. Series resistors limit the current flowing through the LEDs and protect them from excessive current. These indicators offer a simple way to check basic board functionality during development and troubleshooting.

![layout](https://raw.githubusercontent.com/LakshithaV419/Images/main/layout.png)

`Outcome:`

I learned the complete PCB design workflow, including schematic design, component selection, footprint assignment, PCB layout, routing and manufacturing prep, using Altium Designer. I also learned how to configure the STM32 microcontroller, including its GPIO pins, clock settings, and peripheral interfaces, using STM32CubeMX.

![configuration](https://raw.githubusercontent.com/LakshithaV419/Images/main/config.png)


>## TASK 3: Digital DNA

`Objective:` 

Learning Verilog HDL through Creative Circuit Design by building meaningful projects mentioned below:
1) Design and test an 8-bit signed arithmetic unit with operations:
   Addition (00)
   Subtraction (01)
   Comparison (10)
   Absolute difference (11)
   Generate 3 status flags: overflow, zero, negative
2) Design a 2D Population Count Circuit that analyzes a 4×4 binary matrix and provides comprehensive bit counting statistics.
3) Design and test a 4-bit Ripple Carry Adder using a Generate Block. Each gate has a Rise, Fall, and Turn-Off Delay of 3ns, 6ns, and 2ns respectively.
4) Design and test the Capstone Home Light Automation PLA/PAL from Level 1.
5) Design and test a Cellular Automaton of your choice: Rule 90, Rule 110, or 16x16 Conway's Game of Life.
6) Build an alarm system using Verilog and simulate it on a Basys3 FPGA.

`Theory:` 

Differences between implementation code and testbench code in Verilog:
Implementation code in Verilog describes the actual hardware logic of a system and is intended to be synthesized onto physical devices like FPGAs or ASICs. It defines how inputs are processed to produce outputs using constructs such as continuous assignments or procedural blocks, and it avoids simulation-only elements like delays. In contrast, testbench code is used purely for simulation and verification of the design. It generates input stimuli, observes outputs, and checks correctness using features like time delays, system tasks, and monitoring statements, which are not synthesizable. While implementation code represents the circuit itself, the testbench acts as a virtual environment to test and validate that the design behaves as expected before hardware realization.

#### 1. 8 - bit signed ALU

implementation code:

   ```verilog
module alu(
    input [7:0] a,b,
    input [1:0] opcode,
    output reg [7:0] y,
    output v, z, n,
    output reg a_greaterthan_b, a_lessthan_b, a_equalto_b 
);

wire [7:0] q;
assign q = a-b;
    
wire v_sub;
assign v_sub = ((a[7] != b[7]) && (q[7] != a[7]));

always @ (*) begin : block
    
    // Default assignments
    y = 8'b00000000;
    a_greaterthan_b = 0;
    a_lessthan_b = 0;
    a_equalto_b = 0;
    
    case (opcode)
        2'b00 : y = a + b;
        2'b01 : y = a - b;
        2'b10 : begin
                    if (q == 0)
                        a_equalto_b = 1;
                    else if (q[7] ^ v_sub)
                        a_lessthan_b = 1;
                    else 
                        a_greaterthan_b = 1;
                end
        2'b11 : begin
                    if ($signed(a) >= $signed(b))
                      y = a - b;
                    else
                      y = b - a;
                end
        default: y = 8'b00000000;
    endcase
end

assign z = (y == 8'b00000000); 
assign n = y[7]; 
assign v = (opcode == 2'b00) ?
       ((a[7] == b[7]) && (y[7] != a[7])) :   //If a and b have same sign AND result has different sign
       (opcode == 2'b01) ?
       ((a[7] != b[7]) && (y[7] != a[7])) :   //If a and b have different signs AND result sign ≠ a sign
       1'b0;                                  //For comparision and absolute difference, overflow is not meaningful
           
endmodule
```

testbench code:

```verilog
module alu_tb;

reg [7:0] a, b;
reg [1:0] opcode;
wire [7:0] y;
wire v, z, n;
wire gt, lt, eq;

// Instantiate ALU
alu uut (
    .a(a),
    .b(b),
    .opcode(opcode),
    .y(y),
    .v(v),
    .z(z),
    .n(n),
    .a_greaterthan_b(gt),
    .a_lessthan_b(lt),
    .a_equalto_b(eq)
);

initial begin
    // Monitor values
    $monitor("t=%0t | a=%d b=%d op=%b | y=%d | v=%b z=%b n=%b | gt=%b lt=%b eq=%b",
              $time, a, b, opcode, y, v, z, n, gt, lt, eq);

    // Test cases

    // Addition
    a = 20; b = 10; opcode = 2'b00; #10;
    a = 100; b = 50; opcode = 2'b00; #10;

    // Subtraction
    a = 30; b = 10; opcode = 2'b01; #10;
    a = 10; b = 30; opcode = 2'b01; #10;

    // Comparison
    a = 10; b = 10; opcode = 2'b10; #10;
    a = 20; b = 10; opcode = 2'b10; #10;
    a = 5;  b = 10; opcode = 2'b10; #10;

    // Absolute difference
    a = 20; b = 10; opcode = 2'b11; #10;
    a = 10; b = 20; opcode = 2'b11; #10;

    $finish;
end

endmodule
```
![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/digital_dna%20%281%29.png)

#### 2. 4x4 Population Count Circuit

Calculates the number of 1s in a 16-bit binary matrix. The implementation determines the individual bit counts for all four rows and columns and calculates the total number of 1s in the matrix. 

implementation code:

   ```verilog
module popcnt(
    input [15:0] matrix,
    output [2:0] row0, row1, row2, row3,
    output [2:0] col0, col1, col2, col3,
    output [4:0] total
);
    
assign row3 = matrix[0] + matrix[1] + matrix[2] + matrix[3];
assign row2 = matrix[4] + matrix[5] + matrix[6] + matrix[7];
assign row1 = matrix[8] + matrix[9] + matrix[10] + matrix[11];
assign row0 = matrix[12] + matrix[13] + matrix[14] + matrix[15];

assign col3 = matrix[0] + matrix[4] + matrix[8] + matrix[12];
assign col2 = matrix[1] + matrix[5] + matrix[9] + matrix[13];
assign col1 = matrix[2] + matrix[6] + matrix[10] + matrix[14];
assign col0 = matrix[3] + matrix[7] + matrix[11] + matrix[15];

assign total = row0 + row1 + row2 + row3;

endmodule
```

You cannot use a loop and a count variable in Verilog in the same way as in software languages because Verilog describes hardware, not sequential execution. In software, a loop runs step-by-step over time and updates a variable iteratively, but in Verilog, especially within a combinational `always @(*)` block, a `for` loop is unrolled during synthesis into parallel hardware. This means the operations happen simultaneously rather than sequentially. Although you can write a loop with a count variable, it does not behave like a running counter; instead, it is converted into a network of adders. Therefore, the concept of “incrementing a count over iterations” does not apply unless you use clocked (sequential) logic, and for simple designs, direct expressions or structured adders are often clearer and more predictable.

testbench code:

```verilog
module popcnt_tb;

reg [15:0] matrix;
wire [2:0] row0, row1, row2, row3;
wire [2:0] col0, col1, col2, col3;
wire [4:0] total;

// Instantiate DUT
popcnt uut (
    .matrix(matrix),
    .row0(row0), .row1(row1), .row2(row2), .row3(row3),
    .col0(col0), .col1(col1), .col2(col2), .col3(col3),
    .total(total)
);

initial begin
    $monitor("t=%0t matrix=%b | row=%d %d %d %d | col=%d %d %d %d | total=%d",
              $time, matrix,
              row0, row1, row2, row3,
              col0, col1, col2, col3,
              total);

    // Test cases
    matrix = 16'b1100_1000_1011_1111; #10;
    matrix = 16'b1100_1000_1011_1100; #10;
    matrix = 16'b1100_1000_1011_1000; #10;
    matrix = 16'b1100_1000_1011_0000; #10;

    $finish;
end

endmodule

```
![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/digital_dna%20%283%29.png)

#### 3. 4-bit Ripple Carry Adder

The circuit adds two 4-bit binary numbers along with an input carry to produce a 4-bit sum and a final carry output. It uses four full-adder stages connected in sequence, where the carry generated at each stage propagates to the next stage. Gate propagation delays affect the time taken for the final output to stabilise.

implementation code:

   ```verilog
module full_adder (
    input a, b, cin,
    output sum, cout
);

wire x1, x2, x3;

// Using continuous assignments with #(Rise, Fall, Turn-off)
// This compiles in Vivado and matches the 3ns, 6ns, 2ns requirement.
assign #(3,6,2) x1 = a ^ b;
assign #(3,6,2) sum = x1 ^ cin;

assign #(3,6,2) x2 = a & b;
assign #(3,6,2) x3 = x1 & cin;

assign #(3,6,2) cout = x2 | x3;

endmodule


module rca_4bit (
    input [3:0] a, b,
    input cin,
    output [3:0] sum,
    output cout
);

wire [4:0] c;
assign c[0] = cin;

genvar i;

generate
    for (i = 0; i < 4; i = i + 1) begin : stage
        full_adder FA (
            .a(a[i]),
            .b(b[i]),
            .cin(c[i]),
            .sum(sum[i]),
            .cout(c[i+1])
        );
    end
endgenerate

assign cout = c[4];

endmodule
```

testbench code:

```verilog
// ---------------------------------------------------------
// Testbench for 4-bit Ripple Carry Adder
// ---------------------------------------------------------
module tb_rca_4bit;

    // Inputs (reg type because they are driven in initial block)
    reg [3:0] a;
    reg [3:0] b;
    reg cin;

    // Outputs (wire type because they are driven by the module)
    wire [3:0] sum;
    wire cout;

    // Instantiate the Unit Under Test (UUT)
    rca_4bit uut (
        .a(a), 
        .b(b), 
        .cin(cin), 
        .sum(sum), 
        .cout(cout)
    );

    initial begin
        // Initialize Inputs
        a = 0; b = 0; cin = 0;

        // Monitor changes in signals
        $monitor("Time = %0t ns | a = %b (%0d), b = %b (%0d), cin = %b | sum = %b (%0d), cout = %b", 
                 $time, a, a, b, b, cin, sum, sum, cout);

        // Test case 1: 0 + 0 + 0
        #100 a = 4'b0000; b = 4'b0000; cin = 0;
        
        // Test case 2: 5 + 3 + 0 = 8 (No carry out)
        #100 a = 4'b0101; b = 4'b0011; cin = 0;
        
        // Test case 3: 15 + 1 + 0 = 16 (Carry out, sum overflow)
        #100 a = 4'b1111; b = 4'b0001; cin = 0;
        
        // Test case 4: 7 + 8 + 1 = 16 (Carry out, sum overflow)
        #100 a = 4'b0111; b = 4'b1000; cin = 1;
        
        // Test case 5: 10 + 5 + 1 = 16 (Carry out, sum overflow)
        #100 a = 4'b1010; b = 4'b0101; cin = 1;

        // Wait for worst-case propagation delay before finishing.
        // 4 full adders in series. Each FA has a max delay of ~18ns (3ns XOR + 3ns XOR + 3ns AND + 3ns OR).
        // 4 * 18ns = 72ns. Waiting 100ns ensures all signals settle.
        #100 $finish;
    end

endmodule
```

![rca](https://raw.githubusercontent.com/LakshithaV419/Images/main/rca.png)

#### 4. Home Light Automation System

implementation code:

   ```verilog

module light_automation(
    input M, L, T, O,
    output y1, y2, y3
);

// Light 1: Hall / corridor
assign y1 = O | (M & L & T);

// Light 2: Bedroom
assign y2 = O | (L & T);

// Light 3: Outdoor / garden
assign y3 = O | (M & T);

endmodule
```

testbench code:

```verilog
module home_light_automation_tb;

reg M, L, T, O;
wire y1, y2, y3;

light_automation uut (     
    .M(M), .L(L), .T(T), .O(O),
    .y1(y1), .y2(y2), .y3(y3)
);

initial begin

    $monitor("M=%b L=%b T=%b O=%b | y1=%b y2=%b y3=%b", M,L,T,O,y1, y2, y3);
    
    {M,L,T,O} = 4'b0000; #10;
    {M,L,T,O} = 4'b0001; #10;
    {M,L,T,O} = 4'b0010; #10;
    {M,L,T,O} = 4'b0011; #10;
    {M,L,T,O} = 4'b0100; #10;
    {M,L,T,O} = 4'b0101; #10;
    {M,L,T,O} = 4'b0110; #10;
    {M,L,T,O} = 4'b0111; #10;
    {M,L,T,O} = 4'b1000; #10;
    {M,L,T,O} = 4'b1001; #10;
    {M,L,T,O} = 4'b1010; #10;
    {M,L,T,O} = 4'b1011; #10;
    {M,L,T,O} = 4'b1100; #10;
    {M,L,T,O} = 4'b1101; #10;
    {M,L,T,O} = 4'b1110; #10;
    {M,L,T,O} = 4'b1111; #10;
    
    $finish;
    
end

endmodule
```

![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/digital_dna%20%282%29.png)


#### 5. Cellular Automation - 90 Rule

The circuit adds two 4-bit binary numbers along with an input carry to produce a 4-bit sum and a final carry output. It uses four full-adder stages connected in sequence, where the carry generated at each stage propagates to the next stage. Gate propagation delays affect the time taken for the final output to stabilise.

implementation code:

   ```verilog
module cell_aut(
    input clk,
    input rst,
    input load,
    input [15:0] seed,
    output reg [15:0] state
);

    wire [15:0] next_state;

    // Boundary conditions (wrap-around)
    assign next_state[0]  = state[15] ^ state[1];
    assign next_state[15] = state[14] ^ state[0];

    // Internal cells: next_state[i] = left XOR right
    genvar i;
    generate
        for (i = 1; i < 15; i = i + 1) begin : ca_cells
            assign next_state[i] = state[i-1] ^ state[i+1];
        end
    endgenerate

    // Sequential logic for state update
    always @(posedge clk or posedge rst) begin
        if (rst) begin
            state <= 16'b0;
        end else if (load) begin
            state <= seed;
        end else begin
            state <= next_state;
        end
    end
   
endmodule

```

testbench code:

```verilog
module cell_aut_tb;

    reg clk;
    reg rst;
    reg load;
    reg [15:0] seed;
    wire [15:0] state;

    // Instantiate the Unit Under Test (UUT)
    cell_aut uut (
        .clk(clk),
        .rst(rst),
        .load(load),
        .seed(seed),
        .state(state)
    );

    // Clock generation (10ns period)
    initial begin
        clk = 0;
        forever #5 clk = ~clk;
    end

    // Test sequence
    initial begin
        // Initialize Inputs
        rst = 1; load = 0; seed = 16'h0000;
        
        #20 rst = 0; 
        
        // Load a single 1 at the rightmost cell
        #10 load = 1; seed = 16'h0001;
        #10 load = 0;

        // Run for 10 generations (10 clock cycles)
        #1000 $finish;
    end

    // Monitor the state on every clock edge
    initial begin
        $monitor("Time = %0t ns | State = %b", $time, state);
    end

endmodule
```
![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/cellular%20automation.png)

#### 6. Alarm System - Simulated on Basys3 FPGA

The circuit monitors door, window, and motion sensor inputs to detect potential intrusions. When the system is armed, activation of any one of these sensors triggers the alarm output. Individual LED outputs indicate the status of the sensors, while separate indicators show whether the system is armed. The reset input disables the alarm and clears the indicator outputs.

implementation code:

```verilog
module alarm(
    input  wire arm,
    input  wire door,
    input  wire window,
    input  wire motion,
    input  wire reset,

    output reg alarm,
    output reg armed,
    output reg door_led,
    output reg window_led,
    output reg motion_led
);

always @(*) begin

    if (reset) begin
        alarm      = 1'b0;
        armed      = 1'b0;
        door_led   = 1'b0;
        window_led = 1'b0;
        motion_led = 1'b0;
    end
    else begin
        armed      = arm;
        door_led   = door;
        window_led = window;
        motion_led = motion;

        if (arm && (door || window || motion))
            alarm = 1'b1;
        else
            alarm = 1'b0;
    end

end

endmodule

```

testbench code:

```verilog
module alarm_tb;

    // Inputs
    reg arm;
    reg door;
    reg window;
    reg motion;
    reg reset;

    // Outputs
    wire alarm;
    wire armed;
    wire door_led;
    wire window_led;
    wire motion_led;

    // Instantiate the Unit Under Test (UUT)
    alarm uut (
        .arm(arm),
        .door(door),
        .window(window),
        .motion(motion),
        .reset(reset),
        .alarm(alarm),
        .armed(armed),
        .door_led(door_led),
        .window_led(window_led),
        .motion_led(motion_led)
    );

    initial begin

        // Display values in Vivado console
        $monitor("Time=%0t | Reset=%b Arm=%b Door=%b Window=%b Motion=%b | Alarm=%b Armed=%b",
                 $time, reset, arm, door, window, motion, alarm, armed);

        // Initial state
        reset = 1;
        arm = 0;
        door = 0;
        window = 0;
        motion = 0;

        #10;

        // Release reset
        reset = 0;

        // Test 1: System disarmed, no sensors
        arm = 0;
        door = 0;
        window = 0;
        motion = 0;

        #10;

        // Test 2: System armed, no intrusion
        arm = 1;
        door = 0;
        window = 0;
        motion = 0;

        #10;

        // Test 3: Door opened
        door = 1;

        #10;

        // Test 4: Door closed
        door = 0;

        #10;

        // Test 5: Window opened
        window = 1;

        #10;

        // Test 6: Motion detected
        window = 0;
        motion = 1;

        #10;

        // Test 7: Multiple sensors active
        door = 1;
        window = 1;
        motion = 1;

        #10;

        // Test 8: Disarm system while sensors are active
        arm = 0;

        #10;

        // Test 9: Reset system
        reset = 1;

        #10;

        $finish;

    end

endmodule
```

Constraints file:

```
#SWITCH
set_property -dict { PACKAGE_PIN R3    IOSTANDARD LVCMOS33 } [get_ports {motion}]
set_property -dict { PACKAGE_PIN W2    IOSTANDARD LVCMOS33 } [get_ports {window}]
set_property -dict { PACKAGE_PIN U1    IOSTANDARD LVCMOS33 } [get_ports {door}]
set_property -dict { PACKAGE_PIN T1    IOSTANDARD LVCMOS33 } [get_ports {arm}]
set_property -dict { PACKAGE_PIN R2    IOSTANDARD LVCMOS33 } [get_ports {reset}]

#LED
set_property -dict { PACKAGE_PIN U16   IOSTANDARD LVCMOS33 } [get_ports {alarm}]
set_property -dict { PACKAGE_PIN U3    IOSTANDARD LVCMOS33 } [get_ports {motion_led}]
set_property -dict { PACKAGE_PIN P3    IOSTANDARD LVCMOS33 } [get_ports {window_led}]
set_property -dict { PACKAGE_PIN N3    IOSTANDARD LVCMOS33 } [get_ports {door_led}]
set_property -dict { PACKAGE_PIN P1    IOSTANDARD LVCMOS33 } [get_ports {armed}]

## Configuration options, can be used for all designs
set_property CONFIG_VOLTAGE 3.3 [current_design]
set_property CFGBVS VCCO [current_design]

## SPI configuration mode options for QSPI boot, can be used for all designs
set_property BITSTREAM.GENERAL.COMPRESS TRUE [current_design]
set_property BITSTREAM.CONFIG.CONFIGRATE 33 [current_design]
set_property CONFIG_MODE SPIx4 [current_design]
```
![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/alarm%20system.png)
![fpga sim](https://raw.githubusercontent.com/LakshithaV419/Images/main/fpga%20sim.png)

link to [simulation video on Basys3 fpga](https://youtu.be/FsfM2JCDAvU)

`Outcomes:`
I learnt modular and test-driven Verilog design, simulation/debugging in Vivado.
Through this I built a strong foundation for VLSI, FPGA, and digital logic design.


>## TASK 4: The Great Timing Heist

`Objective:` 

To understand and perform Static Timing Analysis (STA) using AMD Vivado, analyse setup and hold timing reports, identify critical paths, and evaluate whether the design satisfies the specified timing constraints.

`Theory:`

Static Timing Analysis is a method used to verify the timing behaviour of a digital circuit without requiring functional simulation. It analyses signal propagation delays between sequential elements to determine whether data reaches its destination within the required timing limits. Important parameters include setup time, hold time, slack, critical paths, logic delay, routing delay, and clock skew.

The timing analysis was performed on the pipelined RISC-V processor design using AMD Vivado. The Design Timing Summary and detailed setup and hold reports were examined to evaluate the timing performance of the circuit.

![summary](https://raw.githubusercontent.com/LakshithaV419/Images/main/timing%20summary.png)

1. Setup Timing Analysis

The setup timing report shows a Worst Negative Slack (WNS) of 1.078 ns, with a Total Negative Slack (TNS) of 0 ns and zero failing endpoints. The critical setup path extends from `mem_wb/rd_out_reg[0]/C` to `ex_mem/ALU_Result_out_reg[25]/D`. The total data path delay is 8.893 ns, consisting of 3.189 ns of logic delay and 5.704 ns of routing delay, against a 10 ns timing requirement. The positive slack indicates that the setup timing constraint is satisfied.

![setup1](https://raw.githubusercontent.com/LakshithaV419/Images/main/setup1.png)

![setup2](https://raw.githubusercontent.com/LakshithaV419/Images/main/setup2.png)

2. Hold Timing Analysis

The hold timing report shows a Worst Hold Slack (WHS) of 0.044 ns, with a Total Hold Slack (THS) of 0 ns and zero failing endpoints. The critical hold path extends from ex_mem/WriteData_out_reg[7]_rep_1/C to data_memory/memory_reg[207][7]/D. The data path delay is 0.372 ns, comprising 0.141 ns of logic delay and 0.231 ns of routing delay. The positive hold slack indicates that the hold timing constraint is satisfied, although the margin is relatively small.

![hold1](https://raw.githubusercontent.com/LakshithaV419/Images/main/hold1.png)

![hold2](https://raw.githubusercontent.com/LakshithaV419/Images/main/hold2.png)

3. Pulse Width Analysis

The Worst Pulse Width Slack (WPWS) is 4.500 ns, while the Total Pulse Width Negative Slack (TPWS) is 0 ns. There are no failing endpoints, indicating that the pulse-width timing requirements are satisfied.

4. Critical Path Analysis

The critical setup path has 14 logic levels and a total delay of 8.893 ns. Routing contributes approximately 64.14% of the total data path delay, while logic contributes approximately 35.86%. This indicates that interconnect delays account for a larger portion of the critical path delay than the logic elements themselves. 
The critical hold path has 0 logic levels and a total data path delay of 0.372 ns. Routing contributes approximately 62.15% of the total data path delay, while logic contributes approximately 37.85%. This indicates that routing delays account for a larger portion of the minimum data path delay, which is important for ensuring that hold-time requirements are satisfied.

`Outcome:` 

Static Timing Analysis was successfully performed on the pipelined RISC-V processor using AMD Vivado. The results show positive setup, hold, and pulse-width slack, with zero failing endpoints and all specified timing constraints satisfied. The analysis also identified routing delay as the dominant contributor to the critical setup path, providing insight into the timing behaviour and potential areas for future optimisation of the FPGA design.



>## TASK 5: Logic Lore

`Objective:` 

To explore FPGA Architecture, understand the following theoretically:
Basic Xilinx Architecture
Configurable Logic Block (CLB)
Switch Matrix
How they combine with memory to form a basic FPGA tile

`Theory:`

#### Concept of FPGA:

###### What is an FPGA?
An FPGA (Field Programmable Gate Array) is a special chip that you can configure (program) even after it is manufactured.
Instead of being fixed like a normal IC, you can design your own hardware circuit inside it.
Can implement any digital circuit
Very fast due to parallel processing
Reprogrammable → flexible

###### Main Components:

1. LUT (Look-Up Table)
   Performs logic operations (AND, OR, NOT, etc.)
   You give inputs → LUT gives output based on stored logic

2. Flip-Flop
   Stores the output of LUT
   Works like memory (1-bit storage)

3. Interconnects (Wires)
   Connect different blocks together
   Fully programmable → you decide how signals flow

4. I/O Blocks (Input/Output Pads)
   Allow signals to enter and leave the FPGA
   
###### How everything works together:
Input comes from I/O
Goes to LUT (logic happens)
Output stored in Flip-Flop
Sent through wires to other blocks or output

###### Advanced Features (Modern FPGA):
Besides basic blocks, modern FPGAs also include:
Block RAM → built-in memory
DSP slices → fast math operations
PLL (Phase-Locked Loop) → controls clock speed
High-speed communication modules
Memory controllers
These make FPGA very powerful (almost like a custom processor)

###### About Xilinx:
One of the leading FPGA companies
Their FPGAs can even:
Run operating systems like Linux
Include embedded processors

###### Applications:
Basically, wherever high-speed and flexible hardware is needed:
Automotive systems (self-driving, sensors)
Communication (5G, networking)
Medical devices
Video processing & broadcasting
AI & data centers
Aerospace & defense

#### Detailed understanding of FPGA architecture:

FPGA stands for Field Programmable Gate Array. It is essentially an array of logical elements that are interconnected, where “gate array” refers to this structured arrangement of logic blocks, and “programmable” means that the internal configuration can be changed or reprogrammed at any time. 
For example, a design implementing an AND operation can later be erased and replaced with an OR operation or any other logic. This reprogrammability is the main advantage of FPGAs, allowing users to design and modify logic circuits as required.

##### The basic architecture of FPGA

![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/logic%20lore%20%283%29.png)

The basic architecture of an FPGA consists of several components. The outer part of the FPGA contains I/O pads (or I/O blocks), which are placed around all four sides of the chip. These I/O pads allow the FPGA to communicate with external devices, enabling data to be sent to or received from external circuits. Since they are available on all sides, connections can be made easily without long wiring, regardless of where the external device is located.

Inside the FPGA, the green blocks represent Configurable Logic Blocks (CLBs), which are the fundamental building blocks of the FPGA. These CLBs perform the actual logic operations and are often referred to as the “heart” of the FPGA. Internally, a CLB consists of a Look-Up Table (LUT), a D flip-flop, and a multiplexer. The LUT implements logic functions based on a truth table, typically supporting a limited number of inputs (for example, a 4-input LUT can implement any logic function with up to four inputs). If more inputs are required, multiple CLBs can be combined.
The D flip-flop is used to store or delay the output of the LUT, while the multiplexer selects between the direct LUT output and the delayed output from the flip-flop, depending on the control signal. Delayed version of output is clocked version of output. This combination allows both combinational and sequential logic to be implemented within a CLB.

![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/logic%20lore%20%284%29.png)

The red lines represent interconnects, which are used to transfer data between different CLBs.Interconnects are used to connect the configurable logic blocks both horizontally and vertically across the FPGA. These interconnections are spread throughout the entire chip and are responsible for transferring data between different CLBs. For example, if data generated in one CLB needs to be sent to another CLB, it travels through these horizontal and vertical interconnect lines. Their main purpose is to ensure that data can be accessed and transferred easily to any required location within the FPGA.

The blue blocks represent the switch matrix (or switch blocks), which enable routing of signals between horizontal and vertical interconnect lines.The switch matrix is responsible for connecting horizontal and vertical interconnect lines. Without it, there would be no way to route signals between different directions. Each CLB is surrounded by interconnects and switch matrices, allowing data to be transferred in any direction. This provides high flexibility and simplifies routing within the FPGA.

![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/logic%20lore%20%285%29.png)

Internally, the switch matrix consists of multiple programmable switches that control the connections between interconnect lines. When a switch is turned ON, a connection is established and data can flow; when it is OFF, the connection is broken. Each switch is typically implemented using a transistor. At every switching point, there are multiple transistors (for example, six pass transistors) that allow data to be routed in different directions, such as from top to bottom, top to left, or top to right, depending on which transistor is activated.

![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/logic%20lore%20%286%29.png)

These switches are controlled by memory cells. If a memory cell stores a logic ‘1’, the corresponding transistor turns ON, and if it stores a ‘0’, the transistor remains OFF. These memory cells hold the configuration data of the FPGA, and based on this stored data, the routing paths are established or disconnected. The memory used for this purpose can be RAM or ROM, depending on the FPGA technology.

![alt text](https://raw.githubusercontent.com/LakshithaV419/Images/main/logic%20lore%20%287%29.png)

`Outcome:` 

I understood the structure and function of FPGA components and comprehended how CLBs and switch matrices contribute to FPGA flexibility.



>## TASK 6: Silicon Sandbox

`Objective:` 

To build a simple, single FPGA tile and simulate it using Verilog

`Theory:`

An FPGA tile was implemented using Verilog HDL based on the architecture specified in the previous task. The switch matrix consists of four 4:1 multiplexers that provide programmable routing between the four input signals and four output signals. The Configurable Logic Block (CLB) was designed by instantiating a 4-input Look-Up Table (LUT), a D flip-flop, and a 2:1 multiplexer to support configurable combinational and registered outputs. Finally, the top-level `fpga_tile` module integrates the switch matrix and CLB to form a complete FPGA tile, which was tested through simulation using different LUT configurations, routing selections, and control signals.

![sim_o/p](https://raw.githubusercontent.com/LakshithaV419/Images/main/fpga_tile.png)

![lut1](https://raw.githubusercontent.com/LakshithaV419/Images/main/lutconfig1.png)

![lut2](https://raw.githubusercontent.com/LakshithaV419/Images/main/lutconfig2.png)

`Outcome:` 

I learned how to design a basic FPGA tile using Verilog HDL. I gained an understanding of modular design and simulation using testbench.



>## TASK 7: MOS Whisperer

`Objective:` 

To learn Analog VLSI Design techniques by drawing the schematic and layout of CMOS Inverter and CMOS Operational Amplifier.

`Theory:`

### CMOS Inverter

![inverter schematic](https://raw.githubusercontent.com/LakshithaV419/Images/main/inv%20sch.png)

![inverter layout](https://raw.githubusercontent.com/LakshithaV419/Images/main/inv%20lay.png)

The circuit is a CMOS inverter consisting of a PMOS transistor connected to the 1.8 V supply and an NMOS transistor connected to ground. Both transistor gates receive the same input signal, while the output is taken from their common connection. When the input is LOW, the PMOS turns ON and the NMOS turns OFF, pulling the output HIGH. When the input is HIGH, the PMOS turns OFF and the NMOS turns ON, pulling the output LOW. The SPICE transient analysis is used to observe the input and output waveforms and measure propagation delays during switching. In the given simulation, the input pulse varies between 0 V and 1.1 V, allowing the inverter's response to be analysed under these input conditions.

![inverter simulation](https://raw.githubusercontent.com/LakshithaV419/Images/main/inv%20simulation.png)

![inverter measured values](https://raw.githubusercontent.com/LakshithaV419/Images/main/inv%20measured%20values.png)

### CMOS Op-Amp

![opamp schematic](https://raw.githubusercontent.com/LakshithaV419/Images/main/opamp%20sch.png)

![opamp layout](https://raw.githubusercontent.com/LakshithaV419/Images/main/op%20amp%20lay.png)

The CMOS operational amplifier consists of an NMOS differential input pair (M1 and M2), a PMOS current-mirror active load (M3 and M4), a tail current transistor (M5), and a second gain stage formed by PMOS transistor M6 and NMOS transistor M7. M5 provides a bias current to the differential pair, so the sum of the drain currents through M1 and M2 remains approximately constant, assuming M5 operates in saturation and the circuit is functioning in its normal operating region. Depending on the input voltages Vin+ and Vin-, the current is steered between M1 and M2, with the transistor receiving the higher gate voltage generally conducting more current. M3 is diode-connected, meaning its gate and drain are connected, and it establishes the reference current for the PMOS current mirror. Since the gates of M3 and M4 are connected together and their sources are connected to VDD, M4 mirrors the current flowing through M3, provided both transistors operate in saturation and their device characteristics are appropriately matched. The current variations in M1 and M2, together with the current-mirror action of M3 and M4, produce a voltage variation at the first-stage output node between M2 and M4. This voltage is then applied to the second stage, where PMOS transistor M6 acts as the amplifying transistor and NMOS transistor M7 acts as the current-sink load. A change in the first-stage voltage changes the gate-to-source voltage of M6, modifying its drain current. This changes the voltage at the output node, Vout, thereby providing additional voltage gain. The compensation capacitor connected between the first-stage output and the final output helps improve frequency stability, while the output load capacitor represents the capacitance driven by the amplifier. Overall, the two stages provide high voltage gain by first converting the differential input voltage into a single-ended signal and then amplifying that signal to produce the final output voltage.

![opamp simulation]()
![opamp measured values]()

`Outcome:` 

I learned to use electric binary. I learnt the working of CMOS Inverter and Op-Amp as well the analysis of the simulated outputs in LTSpice. I also learned how the transistor strengths affect the performance of the circuit.



>## TASK 8: Keep Calm & ROS On

`Objective:` 

To in stall and configure ROS 2 Humble on Ubuntu 22.04 and understand the fundamentals of ROS 2 communication by creating publisher and subscriber nodes and testing them using the Turtlesim simulator.

`Theory:`

![initial movement command](https://raw.githubusercontent.com/LakshithaV419/Images/main/initial%20movement%20command.jpeg)

![initial movement turtle](https://raw.githubusercontent.com/LakshithaV419/Images/main/initial%20movement%20turtle.jpeg)

1. ROS 2 Environment Setup

Ubuntu 22.04 was used as the operating system for installing and running ROS 2 Humble Hawksbill. The ROS 2 environment was configured to enable the execution of nodes and communication between them. The terminal was used to execute ROS 2 commands and monitor system activity.

2. Nodes

Nodes are individual executable units in ROS 2 that perform specific tasks. A robot application can consist of multiple nodes, each responsible for a particular function, such as controlling movement, reading sensors, or processing data. In this task, separate publisher and subscriber nodes were used to demonstrate communication between independent processes.

3. Topics

Topics are named communication channels through which ROS 2 nodes exchange data. They use a publish-subscribe communication model, allowing a publisher to send messages and one or more subscribers to receive them. ROS 2 commands such as ros2 node list and ros2 topic list were used to inspect active nodes and available topics.

4. Publisher Node

The publisher node was implemented to send velocity commands to the Turtlesim simulator through the /turtle1/cmd_vel topic using the geometry_msgs/msg/Twist message type. The velocity commands specify the turtle's linear and angular velocities, enabling it to move forward, backward, or rotate within the simulation environment.

5. Subscriber Node

The subscriber node listens to the /turtle1/pose topic, which publishes the turtle's current position and orientation using the turtlesim/msg/Pose message type. The node receives pose messages and logs the turtle's x-coordinate, y-coordinate, and orientation angle (theta). This demonstrates how a ROS 2 node can monitor the state of a simulated robot.

6. Turtlesim Simulation

Turtlesim is a lightweight ROS 2 simulator used to understand basic robotics concepts and communication. It provides a graphical environment in which the turtle's movement can be observed in response to velocity commands. The simulator's topics and node behaviour were examined to understand how commands are transmitted and how pose information is published.

#### Implementation and Testing

The publisher and subscriber nodes were executed alongside the Turtlesim simulator. The publisher sent velocity commands to control the turtle's movement, while the subscriber received and displayed the corresponding pose information. ROS 2 command-line tools were used to inspect the active nodes and topics.

link to [video](https://youtu.be/Kk0VV77LNqM)

![active list](https://raw.githubusercontent.com/LakshithaV419/Images/main/active%20list.jpeg)

`Outcome:` 

The task provided practical experience in installing and configuring ROS 2 Humble on Ubuntu 22.04 and understanding the concepts of nodes, topics, publishers, and subscribers. It also demonstrated how to control a simulated robot using velocity commands and monitor its position through pose data. This established a foundation for developing more advanced ROS 2 applications and integrating multiple components in robotic systems.
