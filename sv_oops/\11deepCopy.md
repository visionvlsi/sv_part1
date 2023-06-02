

```
class first;
    int data = 12;
    function first copy();
    copy = new();
    copy.data = data;
  endfunction
endclass
 
class second;
  int ds = 34;
  first f1;
  function new();
    f1 = new();
  endfunction
  
  function second copy();
    copy = new();
    copy.ds = ds;
    copy.f1 = f1.copy;    
  endfunction

endclass
 
module tb;
  second s1, s2;
  initial begin
    s1 = new();
    s2 = new();
    s1.ds = 45;
    s2 = s1.copy();
    $display("Value of s2 : %0d", s2.ds);
    s2.ds = 78;
    $display("Value of s1 : %0d", s1.ds);
    s2.f1.data = 98;
    $display("Value of s1 : %0d", s1.f1.data);
  end
endmodule
```

```
// Code your testbench here
// or browse Examples
class a;
  int i;
endclass

class b extends a;
  a a1=new();
  task disp(a a1);
    this.a1 = new a1;
  endtask
endclass

module tb;
  b b1,b2;
  
  initial begin
    b1 = new();
    b2 = new();
    b1.a1.i = 100;
    b2.disp(b1.a1);
    $display("%d %d",b1.a1.i,b2.a1.i);
    b2.a1.i=200;
    $display("%d %d",b1.a1.i,b2.a1.i);
  end
endmodule
```
