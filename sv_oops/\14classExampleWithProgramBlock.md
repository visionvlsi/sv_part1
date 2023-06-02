
```
class simple;
int i,j;
task printf();
$display(i,j);
endtask
endclass

program main;
initial begin
simple obj_1;
simple obj_2;
obj_1=new();
obj_2=new();
obj_1.i=2;
obj_1.j=5;
obj_2.i=4;
obj_1.printf();
obj_2.printf();
end
endprogram
```
