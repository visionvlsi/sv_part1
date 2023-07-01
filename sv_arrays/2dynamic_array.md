#### The following is the dynamic array example 

- Write code for Dynamic Array - Consider a Dynamic array which size is '0' initially
- resize the array with '4' and assign a value into location 2, 3
- Create a d_arr2 and resize the array by preserving the data 

```
module dynamic_array;
  
  //dynamic array declaration
  bit d_arr1[];
  integer d_arr2[];
  //integer d_arr3[];

  initial begin
    $display("Before Memory Allocation");
    $display("\tSize of d_array1 %0d",d_arr1.size());
    $display("\tSize of d_array2 %0d",d_arr2.size());

    //memory allocation
    d_arr1 = new[4]; 
    
    $display("After Memory Allocation");
    $display("\tSize of d_array1 %0d",d_arr1.size());
    
    
    d_arr1[2] = 5; d_arr1[3] = 7; 
    

    $display("--- d_array1 Values are ---");
    $display("d_arr1[2] = %0d, d_arr1[3] = %0d",d_arr1[2], d_arr1[3]);
    $display("---------------------------------");
    
    d_arr2 = new[6];
    $display("\tSize of d_array2 %0d",d_arr2.size());
    
    d_arr2 = {6, 1, 4, 9, 7, 2};
    $display("--- d_array2 Values are ---");
    foreach(d_arr2[i])   $display("\td_aaray2[%0d] = %0d",i, d_arr2[i]);
    $display("---------------------------------");
    
    d_arr2 = new[8](d_arr2);
    $display("\tSize of d_array2 %0d",d_arr2.size());
    $display("--- d_array2 Values are ---");
    foreach(d_arr2[i])   $display("\td_aaray2[%0d] = %0d",i, d_arr2[i]);
    $display("---------------------------------");
    
  end

endmodule
```
