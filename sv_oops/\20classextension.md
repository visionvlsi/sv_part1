
```
// Code your testbench here
// or browse Examples
class x;
  task disp1();
    bit [3:0]a=10;
    byte b=50;
    $display("%d %d",a,b);
  endtask
endclass

class y extends x;
  task disp2();
    bit [3:0]a=15;
    byte b=60;
    $display("%d %d",a,b);
  endtask
endclass

module test;
  y y1=new();//handle and object created
  
  initial begin
    y1.disp1();
    y1.disp2();
  end
 endmodule
  ```
