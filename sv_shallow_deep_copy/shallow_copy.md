#### Example-1 shallow copy
```
class transaction;
  bit [31:0] data;
endclass

module class_example;
  transaction tr1, tr2;
  initial begin
    tr1 = new();
    tr1.data = 5;
    tr2 = tr1;
    $display("tr1.data = %0h", tr1.data);
    $display("tr2.data = %0h", tr2.data);
    
    tr2.data = 10;
    $display("tr2.data = %0h", tr2.data);
    $display("tr1.data = %0h", tr1.data);
  end
endmodule
```
#### Example-2 Shallow copy
```
class A;
  int m = 15;
  string n= "sun";
endclass
 
class B;
  int i = 20;
  string j= "moon";
  A a = new;
endclass
 
module shallow;
  B b1, b2;
  initial begin
    b1 = new;
    b2 = new b1;// shallow copy method 
    
    $display("b1.i = %0d | b1.j = %0s | b1.a.m=%0d | b1.a.n=%0s",b1.i,b1.j,b1.a.m,b1.a.n);
    $display("b2.i = %0d | b2.j = %0s | b2.a.m=%0d | b2.a.n=%0s",b2.i,b2.j,b2.a.m,b2.a.n);
    $display("-----------------------------------------------------");

    b1.i = 30;
    b1.j="star";
    b1.a.m = 25;
    b1.a.n="planet";//Assigns planet to variable “n” shared by both b1 & b2
    
    $display("b1.i = %0d | b1.j = %0s | b1.a.m=%0d | b1.a.n=%0s",b1.i,b1.j,b1.a.m,b1.a.n);
    $display("b2.i = %0d | b2.j = %0s | b2.a.m=%0d | b2.a.n=%0s",b2.i,b2.j,b2.a.m,b2.a.n);
    $display("-----------------------------------------------------");

    b2.i = 40;
    b2.j="earth";
    b2.a.m = 35;
    b2.a.n="saturn";
    
    $display("b2.i = %0d | b2.j = %0s | b2.a.m=%0d | b2.a.n=%0s",b2.i,b2.j,b2.a.m,b2.a.n);
    $display("b1.i = %0d | b1.j = %0s | b1.a.m=%0d | b1.a.n=%0s",b1.i,b1.j,b1.a.m,b1.a.n);

end
endmodule
```
#### Example-3 Shallow copy
```
class error_trans;
  bit [31:0] err_data;
  bit error;
  
  function new(bit [31:0] err_data, bit error);
    this.err_data = err_data;
    this.error = error;
  endfunction
endclass

class transaction;
  bit [31:0] data;
  int id;
  error_trans err_tr;
  
  function new();
    data = 100;
    id = 1;
    err_tr = new(32'hFFFF_FFFF, 1);
  endfunction
  
  function void display();
    $display("transaction: data = %0d, id = %0d", data, id);
    $display("error_trans: err_data = %0h, error = %0d\n", err_tr.err_data, err_tr.error);
  endfunction
endclass

module shallow_copy_example;
  transaction tr1, tr2;
  
  initial begin
    tr1 = new();
    $display("Calling display method using tr1");
    tr1.display();
    
    tr2 = new tr1;
    $display("After shallow copy tr1 --> tr2");
    $display("Calling display method using tr2");
    tr2.display();
    $display("--------------------------------");
    
    tr1.data = 200;
    tr1.id = 2;
    tr1.err_tr.err_data = 32'h1234;
    tr1.err_tr.error = 0;
    
    $display("Calling display method using tr1");
    tr1.display();
    $display("Calling display method using tr2");
    tr2.display();
    
  end
endmodule
```
