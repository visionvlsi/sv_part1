#### The following is the static array example

- Question1:
- Write code for Static Array for data types.
```
module fixedsize_array;
  //declaration of array’s
  int array1[6];               
  int array2[4:0];             
 
  initial begin
    //array initialization
    array1 = '{0,1,2,3,4,5};
    array2 = '{0,1,2,3,4};
   
    //displaying array elements
    $display("-------displaying array1-------");
    foreach(array1[i]) $display("\t array1[%0d] = %0d",i,array1[i]);
 
    $display("-------displaying array2-------");
    foreach(array2[i]) $display("\t array2[%0d] = %0d",i,array2[i]);
 
  end
endmodule
```
