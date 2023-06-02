
```
// Code your testbench here
// or browse Examples
virtual class a;
  int data;
  
  pure virtual function int getdata();
endclass
    
class b extends  a;
  virtual function int getdata();
     data = 32'habcd_abcd;
      return data;
  endfunction
endclass
      
module tb;
  b b1=new();
  initial begin
    $display("%h",b1.getdata());
  end
endmodule
    ```
