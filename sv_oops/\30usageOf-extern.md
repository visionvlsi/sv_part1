
```
// Code your testbench here
// or browse Examples
class packet;
  bit [31:0]addr;
  bit [31:0]data;
  
  //function declaration - extern indicates out-of-body declaration
  extern virtual function void display();
endclass
    
//function implementation outside class body
function void packet::display();
   $display("addr: %d data :%d",addr,data);
endfunction
    
module tb;
  initial begin
    packet p;
    p = new();
    p.addr = 20;
    p.data = 10;
    p.display();
   end
endmodule
```
