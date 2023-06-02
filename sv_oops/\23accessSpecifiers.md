
```
// Code your testbench here
// or browse Examples
class b;
  int i=40;
  local int l=50;
  protected int p=60;
  static int s=80;
  
  task disp();
    $display("%d %d %d %d",i,l,p,s);
  endtask
endclass

class c extends b;
  task disp1();
    i = 45;
    p = 65;
    s = 85;
    $display("%d %d %d",i,p,s);
  endtask
endclass

module test;
  c c1=new();
  
  initial begin
    c1.disp();
    c1.disp1();
     
  end
endmodule
```
