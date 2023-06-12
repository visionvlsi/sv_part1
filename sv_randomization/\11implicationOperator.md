#### Example-1
```
class generator;
  
  randc bit [3:0] a;
  rand bit ce;
  rand bit rst;
  
  constraint control_rst {
    rst dist {0:= 80, 1 := 20};
  }
  
  constraint control_ce {
    ce dist {1:= 80, 0 := 20};
  }
  
  constraint control_rst_ce {
    ( rst == 0 ) -> (ce == 1); 
  }
  
endclass
 
module tb;
  
  generator g;
  
  initial begin
    g = new();
    
    for (int i = 0; i<10 ; i++) begin
      assert(g.randomize()) else $display("Randomization Failed");
      $display("Value of rst : %0b and ce : %0b", g.rst, g.ce);
    end
    
  end
 
endmodule
```
#### Example-2
```
class inside_fn;
  rand bit [1:0] data;
  rand bit [3:0] val;
  constraint con{ data == 3 -> val < 3;}
endclass

module main;
  initial begin
  inside_fn fun = new;
    repeat (20)
      begin
  fun.randomize();
  $display("The value of data = %p and value = %p",fun.data,fun.val);
      end
  end
endmodule
```
