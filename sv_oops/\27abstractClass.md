
```
// Code your testbench here
// or browse Examples
virtual class F;
  bit [31:0]address;
  int data;
endclass

class G extends F;
  function void display();
    this.address = address;
    this.data = data;
    $display("%d %d",address,data);
  endfunction
endclass

module tb;
  initial begin
    G g1 = new();
    g1.address = 20;
    g1.data = 4;
    g1.display();
  end
endmodule
 ```
