#### Case 1-A: randc works

```
class ex1;
    randc bit [3:0]a;
    constraint a_in { a inside {[3:8]};}
endclass

module tb;
  
   ex1 h1;
  
  initial begin
    
   h1=new();
   for(int i=0; i<16; i++) begin
      h1.randomize();
      #1;
      $display($time," The value of a is %0d", h1.a);
    end
  end
endmodule
```
#### Case 1-A: randc works

```
module tb;
  
  class ex1;
    randc bit [3:0]a;
    constraint a_in { a inside {[3:8]};}
  endclass
  
   ex1 h1;
  
  initial begin
    
    
   h1=new();
   for(int i=0; i<16; i++) begin
      h1.randomize();
      #1;
      $display($time," The value of a is %0d", h1.a);
    end
  end
endmodule
```

#### Case 2: randc does not work

```
module tb;
  
  class ex1;
    randc bit [3:0]a;
    constraint a_in { a inside {[3:8]};}
  endclass
  
   ex1 h1;
  
  initial begin
    
      for(int i=0; i<16; i++) begin
      h1=new();
      h1.randomize();
      #1;
      $display($time," The value of a is %0d", h1.a);
    end
  end
endmodule
```
