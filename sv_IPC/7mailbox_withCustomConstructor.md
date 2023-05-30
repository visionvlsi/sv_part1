
```
class generator;
  
  int data = 56;
  
  mailbox mbx; ///gen2drv
  
  function new(mailbox mbx);
    this.mbx = mbx;
  endfunction
  
  task run();
    mbx.put(data);
    $display("[GEN] : SENT DATA : %0d", data);    
  endtask
    
endclass
 
class driver;
  int datac = 0;
  mailbox mbx;
  
  function new(mailbox mbx);
    this.mbx = mbx;
  endfunction
  
  task run();
    mbx.get(datac);
    $display("[DRV] : RCVD Data : %0d", datac);
  endtask
   
endclass
 
module tb;
  
  generator gen;
  driver drv;
  mailbox mbx;
   
  initial begin
    mbx = new();  
    gen = new(mbx);
    drv = new(mbx);
 
    gen.run();
    drv.run();
      
  end
  
endmodule
```
