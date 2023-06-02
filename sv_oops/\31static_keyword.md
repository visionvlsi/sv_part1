
#### Example-1
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
#### Example-2
```
// Code your testbench here
// or browse Examples
class H;
  //static variable
  static int pkt_num=0;
 
  function new();
    pkt_num++;
  endfunction
  //static function
  static function int static_func;
    $display("value of static variable is %0d",pkt_num);
  endfunction
endclass
  program main_H;
    H h[6];
    initial begin
      for(int i=0;i<$size(h);i++)begin
          h[i]=new();
          //static call using :: operator
           H::static_func();
          //normal calling using instance
          //h[i].static_func();
        end
       end
  endprogram
  ```
