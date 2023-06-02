
```
// Code your testbench here
// or browse Examples
class array;
  rand reg a[2:0][2:0];
  
  function void disp();
    foreach(a[i,j])
      $display("%d %d",i,j,a[i][j]);
  endfunction
endclass

module tb;
  array a1=new();
  
  initial begin
    void'(a1.randomize());
    a1.disp();
  end
endmodule
```
#### 2D Array class with this keyword
```
// Code your testbench here
// or browse Examples
class array;
  reg a[2:0][2:0];
  
  function new(reg a[2:0][2:0]);
    this.a = a;
  endfunction
  
  function void display();
    $display("%p",a);
  endfunction
endclass
  
  module tb;
    initial begin
      array a1;
      a1 = new({'{1,0,1},'{1,1,0},'{1,1,1}});
      a1.display();
    end
  endmodule
  ```
