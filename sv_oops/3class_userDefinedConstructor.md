

```
class first;
  
  int data;
  
  function new(input int datain = 0);
  data = datain;
  endfunction
    
endclass
 
module tb;
  
  first f1;
  
  initial begin
    f1 = new(23);
    $display("Data : %0d", f1.data); 
  end

endmodule

```
