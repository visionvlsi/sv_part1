

```
class first;
    int data = 12;
endclass
 
class second;
  int ds = 34;
  first f1;
  function new();
    f1 = new();
  endfunction
endclass
 
module tb;
  second s1, s2;
  initial begin
    s1 = new();
    s1.ds = 45;
    s2 = new s1;
    $display("Value of ds: %0d", s2.ds);
    s2.ds = 78;
    $display("Value of ds: %0d", s1.ds);
    s2.f1.data = 56;
    $display("Value of data: %0d", s1.f1.data);
  end
endmodule
```

```
// Code your testbench here
// or browse Examples
class D;
  int i;
endclass

module tb;
  D d1,d2;
  
  initial begin
    d1 = new();
    d2 = new();
    d1.i = 100;
    d2 = new d1;
    $display("%d %d",d1.i,d2.i);
    d2.i = 200;
    $display("%d %d",d1.i,d2.i);
  end
endmodule
```
