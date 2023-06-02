
```
// Code your testbench here
// or browse Examples
class parent;
  bit [31:0] addr;
endclass
 
class child extends parent;
  bit [31:0] data;
endclass
 
module inheritence;
  initial begin
    child c = new();
    c.addr = 10;
    c.data = 20;
    $display("Value of addr = %0d data = %0d",c.addr,c.data);
  end
endmodule
```
