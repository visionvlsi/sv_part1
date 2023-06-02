
```
// Code your testbench here
// or browse Examples
class base;
  virtual task disp();
    $display("iam base");
  endtask
endclass

class derived extends base;
  task disp();
    $display("iam derived");
  endtask
endclass

module tb;
  base b1=new();
  derived d1=new();
  initial begin
    b1.disp();
    b1=d1;
    b1.disp();
  end
endmodule
```
