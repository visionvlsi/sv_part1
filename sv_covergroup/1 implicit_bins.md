#### Example of implicit bins:

```
// Implicit bins example

class pkt;
		rand bit[3:0] addr;
		rand bit[3:0] data;
endclass

module top;

	pkt p=new();
		
		covergroup cg;
			//implicit
			ADDR: coverpoint p.addr;
			DATA: coverpoint p.data;
		endgroup
		 
		 initial 
			begin
				cg c=new();
				repeat(10)
				begin
					p.randomize();
					c.sample();
				end
			end
		 
endmodule
```
[code on EDAPlayground](https://edaplayground.com/x/Nv26)
