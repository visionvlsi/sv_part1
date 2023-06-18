#### Example of explicit bins

```
class pkt;
 rand bit [3:0]addr;
 rand bit [3:0]data;
endclass

module top;
	pkt p=new();
	
	covergroup addr_cg;
			ADDR: coverpoint p.addr{
						//bins
						bins b1={1,11}; //this bin will be covered if these values occur
						bins b2={[1:4]};
						bins b3[]={[5:8]};
						bins b5[]={1,[2:4],8};
						}
          		DATA: coverpoint p.data{
						//bins
						bins b3={1}; 
            					bins b4={[1:4]}; //this bin will be covered if values occur in this range
        					}
	endgroup
	
	initial
	begin
		addr_cg c=new();
		repeat(10)
			begin
                           p.randomize;
                           $display("addr=%d, data=%d", p.addr, p.data);
                           c.sample();
			end
	end
	
endmodule
```
<p align="justify"> In EDAPlayground if Questasim is used the create a file called run.do with the following commands</p><br/>

- run -all
- coverage report -detail

