
```
// Code your testbench here
// or browse Examples
class a;
  task disp();
    $display("iam a");
  endtask
endclass

class b extends a;
  task disp();
    super.disp();
    $display("iam b");
  endtask
endclass

module test;
  b b1;
  initial begin
    b1 = new();
    b1.disp();
  end
endmodule
```
