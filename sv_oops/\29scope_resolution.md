
```
// Code your testbench here
// or browse Examples
class H;
  static int data;
  
  static function void display();
    $display("%d",data);
    data++;
  endfunction
endclass

module tb;
  H h1;
  initial begin
    H::data = 5;
    H::display();
    
    h1 = new();
    
    $display("%d",h1.data);
  end
endmodule
```
