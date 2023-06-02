
```
// Code your testbench here
// or browse Examples
class packet;
  
  //class properties
  int addr;
  byte  data;
  bit		 write;
  string	 pkt_type;
  
  //constructor
  function new();
    addr  = 32'd10;
    data  = 8'd43;
    write = 1;
    pkt_type = "Prasanthi";
  endfunction
  
  //method to display class prperties
  function void display();
    $display("---------------------------------------------------------");
    $display("\t addr  = %0d",addr);
    $display("\t data  = %0h",data);
    $display("\t write = %0d",write);
    $display("\t pkt_type  = %0s",pkt_type);
    $display("---------------------------------------------------------");
  endfunction
  
endclass

module sv_constructor;
  packet pkt;

  initial begin
    pkt = new();
    pkt.display();
  end  
endmodule
```
