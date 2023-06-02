
```
// Code your testbench here
// or browse Examples
class E #(int size=8);
  bit [size-1:0] out;
endclass

module tb;
  
  //Override the default value of 8 with the given values in #()
  E  #(16) e1;
  E  #(.size(8)) e2;
  typedef E#(4) nibble;
  nibble e3;
  
  initial begin
    e1 = new;
    e2 = new;
    e3 = new;
    
    //print the size of "out" variable
    $display("e1.out = %0d bits",$bits(e1.out));
    $display("e2.out = %0d bits",$bits(e2.out));
    $display("e3.out = %0d bits",$bits(e3.out));
  end
endmodule
 ```
