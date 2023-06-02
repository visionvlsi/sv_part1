
```
// Code your testbench here
// or browse Examples
typedef b;//Inform compiler that b1 might be used before actualclass identification

class a;
  b b1;
  task disp();
  $display("iam base");
  endtask
endclass

class b extends a;
  a a1;
  task disp1();
  	$display("iam derived");
  endtask
endclass

module tb;
  a a1=new();
  b b1=new();
  
  initial begin
    a1.disp();
    b1.disp1();
  end
endmodule
```
