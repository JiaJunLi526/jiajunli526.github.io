---
layout: project
type: project
image: img/alu/alu_front.jpg
title: "4-Bit Arithmetic logic unit (ALU)"
date: 2025
published: true
labels:
  - Digital Logic Design
  - Verilog
summary: "A project building and simulating individual operations of an ALU for ECE 260."
---

<div class="text-center p-4">
  <img width="400px" src="../img/alu/alu_req.png" class="img-thumbnail" >
  <img width="400px" src="../img/alu/alu_submath.png" class="img-thumbnail" >
  <img width="500px" src="../img/alu/alu_sub.png" class="img-thumbnail" >
  <img width="200px" src="../img/alu/alu_final.png" class="img-thumbnail" >
</div>

This final project for ECE 260 focused on designing and implementing a simple Arithmetic Logic Unit (ALU) using a combination of truth tables, logic simplification, circuit simulation, and Verilog coding. The project required working through the entire design process manually, which helped me better understand how low-level CPU operations are built from basic logic components.

I started by defining the required operations and constructing truth tables for each one. From these truth tables, I used Karnaugh maps (K-maps) to simplify the Boolean expressions for the logic. This step was important because it reduced the number of gates needed and made the overall design more efficient and easier to implement. After simplifying the equations, I implemented each operation as a separate logic module in the Falstad circuit simulator, which allowed me to visually verify that each circuit behaved as expected.

Once each operation was working correctly on its own, I combined them into a single ALU design using a multiplexer. The multiplexer selects which operation is performed based on the control signal, similar to how a real CPU chooses between arithmetic and logical instructions. This made it clear how multiple independent logic blocks can be integrated into a larger system using control signals.

After validating the logic in Falstad, I translated the design into Verilog, implementing the ALU as a behavioral module. The ALU takes two 4-bit inputs, a 3-bit select signal, and produces a 4-bit output along with zero, overflow, and carry flags. Writing the Verilog reinforced how the high-level logic design maps directly into hardware description code, and how different operations can be selected using a case statement driven by the control input.

Through this project, I gained hands-on experience deriving Boolean equations from truth tables, simplifying them with K-maps, and implementing them in both a circuit simulator and Verilog. More importantly, I developed a better understanding of how fundamental logic design techniques scale into real-world systems such as CPUs. Manually designing each part of the ALU helped demystify how higher-level operations are built from basic components, making the connection between theory and practical hardware design much clearer.

This is the verilog code:
```verilog
module ALU (
  input  [3:0] a, b,
  input  [2:0] s,
  output [3:0] F,
  output Z, V, C
);

  reg [7:0] out;
  
  always @(*) begin
    case (s)
      3'b000: out = 2 * a;
      3'b001: out = a / 2;
      3'b010: out = a * b;
      3'b011: out = a + b;
      3'b100: out = a - b;
      3'b101: out = b - a;
      3'b110: out = a ^ b;
      3'b111: out = a < b;
      default: out = 0;
    endcase
  end

  assign Z = (out == 4'd0);
  assign V = (out > 127 || out < -128);
  assign C = (s == 3'b011 && (out[4] | (a[3] & b[3]))) 
          || (s == 3'b100 && (a[3] < b[3])) 
          || (s == 3'b101 && (b[3] < a[3]));
  assign F = out[3:0];
  
endmodule
```

        
          
        
