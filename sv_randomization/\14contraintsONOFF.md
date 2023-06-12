#### Example-1
```
class generator;
  
  randc bit [3:0] raddr, waddr;
  rand bit wr; ///write to mem
  rand bit oe; ///output enable
  
  constraint wr_c {
    wr dist {0:= 50, 1 := 50};
  }
   
  constraint oe_c {
    oe dist {1:= 50, 0 := 50};
  }
  
  constraint wr_oe_c {
    ( wr == 1 ) -> (oe == 0); 
  }

endclass
 
module tb;
  
  generator g;
  
  initial begin
    g = new();
   
    g.wr_oe_c.constraint_mode(0); ///1 -> COnstraint is on // 0-> constraint is off 
      $display("Constraint Status oe_c : %0d",g.wr_oe_c.constraint_mode()); 
    for (int i = 0; i<20 ; i++) begin
      assert(g.randomize()) else $display("Randomization Failed");
      $display("Value of wr : %0b | oe : %0b | ", g.wr, g.oe);
    end
    
  end
  
endmodule
```
#### Example-2
```
// Code your testbench here
// or browse Examples
class inline;
  rand bit [3:0] a;
  constraint con { a > 3; a < 7 ;}
endclass

module main;
  initial begin
    inline val = new;
    if (val.con.constraint_mode())
      $display("Constraint is enabled");
    else
      $display("Constraint is disabled");
    val.randomize();
    $display("The value of a = %p",val.a);
    val.con.constraint_mode(0);
      if (val.con.constraint_mode())
      $display("Constraint is enabled");
    else
      $display("Constraint is disabled");
    end
endmodule
```
