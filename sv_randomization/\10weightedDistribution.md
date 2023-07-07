#### Example 1
```
//         := vs :/

class first;
  
rand bit wr; // :=
rand bit rd; // :/
  
  rand bit [1:0] var1;
  rand bit [1:0] var2;
  
  constraint data {
    var1 dist {0 := 30, [1:3] := 90}; //0 = 30/300 , 1,2,3 = 90/300 
    var2 dist {0  :/ 30 , [1:3] :/ 90}; //0,1,2,3, = 30/120 = 0.25
  
  }
  
  constraint cntrl {
  
    wr dist {0 := 30 , 1 := 70};
    
    rd dist {0 :/ 30 , 1 :/ 70};
  
  }  
  
endclass
  
module tb;
  
  first f;
  
  initial begin
    f = new();
    
    for(int i = 0; i < 15; i++) begin
      f.randomize();
      $display("Value of Var1(:=) : %0d and Var2(:/) : %0d", f.var1, f.var2);    
    end
    
  end
   
endmodule
```
#### Example 2 write constraint 8bit data, 0-100 for 70% and 101-255 30%
```
class cons;
rand bit [7:0]a;
  constraint x{a dist {[0:100]:/70,[101:255]:/30};}
function void post_randomize();
$display(a);
endfunction
endclass
cons c;
module top;
int count;
initial
begin
c=new;
repeat(100)
begin
c.randomize;
if(c.a<101)
count=count+1;
end
$display("No of entries less than 100 are %0d",count);
$display("No of entries less than 100 are %0d",100-count);
end
endmodule
```
