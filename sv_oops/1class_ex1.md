#### The following is the class example. class_ex1.sv

```
class first;
  
  reg [2:0] data; 
  reg [1:0] data2;

endclass

module tb;
  
  first f;

  initial begin
    f = new(); 
    #1;
    $display("Value of data : %0d and data2 : %0d",f.data, f.data2);
  end

endmodule

```
```
// Code your testbench here
// or browse Examples
class d;
  bit [3:0]a;
  byte b;
  task disp();
    $display("%d %d",a,b);
  endtask
endclass

module tb;
  d d1=new();
  
  initial begin
    d1.a = 15;
    d1.b = 50;
    d1.disp();
  end
endmodule
  ```
