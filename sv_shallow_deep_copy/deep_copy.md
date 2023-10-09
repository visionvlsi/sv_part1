#### Deep copy examples

#### Example-1 deep copy
```
class A;
int m = 15;
string n= "sun";
endclass

class B;
int i = 20;
string j= "moon";
A a = new;

function void copy(B obj_b); //In order to do a “deep” copy, a custom copy method must be created
this.i = obj_b.i;
this.j = obj_b.j;
this.a.m = obj_b.a.m;
this.a.n = obj_b.a.n; //this.a=new obj_b.a
endfunction : copy endclass

module deep;

B b1,b2;

initial begin
b1=new();
b2=new();
b2.copy(b1);//calling deep copy method

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
#### Example-2 deep copy
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

function deep_copy(transaction tr);
this.data = tr.data;
this.id = tr.id;
this.err_tr.err_data = tr.err_tr.err_data;
this.err_tr.error = tr.err_tr.error;
endfunction
endclass

module deep_copy_example;
transaction tr1, tr2;

initial begin
tr1 = new();
$display("Calling display method using tr1");
tr1.display();

tr2 = new();
tr2.deep_copy(tr1);
$display("After deep copy tr1 --> tr2");
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
