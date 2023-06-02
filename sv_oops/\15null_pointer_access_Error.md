
```
class packet;
int length=0;

function new(int l);
length=l;
endfunction
  
endclass

program main;
initial begin
packet pkt;
  #1;
  $display(pkt.length);
end
endprogram
```

#### Null pointer access can be avoided

```
class packet;
int length=0;

function new(int l);
length=l;
endfunction
  
endclass

program main;
initial begin
packet pkt=new(10);
  #1;
  $display(pkt.length);
end
endprogram
```
