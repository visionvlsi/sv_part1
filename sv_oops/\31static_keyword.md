
```
// Code your testbench here
// or browse Examples
class packet;
  rand static bit [31:0]addr;
  rand static bit [31:0]data;
  
  //function declaration - extern indicates out-of-body declaration
  extern virtual function void display();
endclass
    
//function implementation outside class body
function void packet::display();
  this.addr = addr;
  this.data = data;
   $display("addr: %d data :%d",addr,data);
endfunction
    
module tb;
  
  initial begin
    repeat(5) begin
      packet p;
    p = new();
      
      void'(randomize());   
    p.display();
    end
   end
endmodule
```
