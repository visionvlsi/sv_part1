
```
class packet;
  
  //class properties
  bit [31:0] addr;
  bit [31:0] data;
  bit		 write;
  string	 pkt_type;
  
  //constructor
  function new(bit [31:0] addr,data,bit write,string pkt_type);
    this.addr  = addr;
    this.data  = data;
    this.write = write;
    this.pkt_type = pkt_type;
  endfunction
  
  //method to display class prperties
  function void display();
    $display("---------------------------------------------------------");
    $display("\t addr  = %0h",addr);
    $display("\t data  = %0h",data);
    $display("\t write = %0h",write);
    $display("\t pkt_type  = %0s",pkt_type);
    $display("---------------------------------------------------------");
  endfunction
  
endclass

module sv_constructor;
  packet pkt;

  initial begin
    pkt = new(32'h10,32'hFF,1,"Prasanthi");
    pkt.display();
  end
  
endmodule
```
```
// Code your testbench here
// or browse Examples
class d;
  int x;
  bit [3:0]y;
  function new(int x,bit [3:0]y);
    this.x = x;
    this.y = y;
  endfunction
  function void display();
    $display("%d %d",x,y);
  endfunction
endclass

module tb;
  d d1;
  initial begin
    d1 = new(10,5);
    d1.display();
  end
endmodule
```
