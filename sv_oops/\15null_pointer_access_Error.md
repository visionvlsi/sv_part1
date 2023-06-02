
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
pkt.length=10;
end
endprogram
```
