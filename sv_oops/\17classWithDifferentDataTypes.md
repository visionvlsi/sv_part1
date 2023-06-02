
```
// Code your testbench here
// or browse Examples
class packet;
  rand bit[2:0]a;
  rand byte b;
  rand int c;
  string d="naveed";
  
  constraint c1{1<a<5;}
  constraint c2{b>100;}
  constraint c3{c>500;}
  
endclass

module packet;
  //handle and memory is created
  packet p1 = new();
  
  initial begin
    repeat(5) begin
      if(p1.randomize())
        $display("success : %d %d %d %s",p1.a,p1.b,p1.c,p1.d);
      else
        $display("fail : %d %d %d %s",p1.a,p1.b,p1.c,p1.d);
    end
  end
endmodule
```
