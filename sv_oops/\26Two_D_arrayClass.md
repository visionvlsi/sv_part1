
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
