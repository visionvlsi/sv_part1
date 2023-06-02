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
```
// Code your testbench here
// or browse Examples
class a;
  int ch1,ch2,ch3,ch4,ch5,ch6;
  
  function void disp();
   this.ch1  = ch1;
    this.ch2 = ch2;
    this.ch3 = ch3;
    this.ch4 = ch4;
    this.ch5 = ch5;
    this.ch6 = ch6;
    
    $display("%d %d %d %d %d %d",ch1,ch2,ch3,ch4,ch5,ch6);
  endfunction
endclass
  
  module tb;
    a a1=new();
    
    initial begin
      a1.ch1 = 10;
      a1.ch2 = 15;
      a1.ch3 = 20;
      a1.ch4 = 25;
      a1.ch5 = 30;
      a1.ch6 = 35;
      a1.disp();
    end
  endmodule
  ```
