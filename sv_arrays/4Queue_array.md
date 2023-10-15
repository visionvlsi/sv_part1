#### Queues

#### Example-1: 
```
module queues_array;
  //declaration
  bit    [31:0] queue[$]; //unbounded queue
  int    lvar;  
  
  initial begin
    //Queue Initialization:
    queue = {0,1,2,3};
    
    //Size-Method
    $display("\tqueue elements: %0p",queue);
    $display("\tqueue size is %0d",queue.size());
    $display("----------------------------------------------------------------"); 
      
    //Push_front Method
    queue.push_front('h22);
    $display("\tpush_front(22):queue elements: %0p",queue);
    $display("\tqueue size after push_front is %0d",queue.size());
    $display("----------------------------------------------------------------");
    
    //Push_back  Method
    queue.push_back('h44);
    $display("\tpush_back(44):queue elements: %0p",queue);
    $display("\tqueue size after push_back is %0d",queue.size());
    $display("----------------------------------------------------------------");
    
    //Pop_front Method
    lvar = queue.pop_front();
    $display("\tlvar= %0h",lvar);
    $display("\tpop_front():queue elements: %0p",queue);
    $display("\tqueue pop_front value is %0d and size is %0d",lvar,queue.size());
    $display("----------------------------------------------------------------");
    
    //Pop_back Method
    lvar = queue.pop_back();
    $display("\tpop_back():queue elements: %0p",queue);
    $display("\tqueue pop_back value is %0d and size is %0d",lvar,queue.size());
    $display("----------------------------------------------------------------");
    
    //insert method
    queue.insert(4,4);
    $display("\tinsert(4,4):queue elements: %0p",queue);
    $display("\tafter insert method size is %0d",queue.size());
    $display("----------------------------------------------------------------");
    
    //shuffle method
    $display("\tqueue before shuffle: %0p",queue);
    queue.shuffle();
    $display("\tqueue after shuffle: %0p",queue);
    $display("----------------------------------------------------------------");

    //delete method
    queue.delete(3);
    $display("\tqueue's 3rd index is deleted and size is %0d",queue.size());
    queue.delete();
    $display("\tqueue's all elements are deleted and size is %0d",queue.size());
    
  end
endmodule
```
#### Example-2: 
```
module queues_array;
  //declaration
  bit [31:0] q[$:3];  //bounded queue
  
  initial begin
    //Queue Initialization:
    q = {0,1,2,3};
    
    //push_front method: last element will be pushed out
    q.push_front(8);
    $display("\tqueue elements: %0p",q);
    
//     foreach(q[i]) $display("\tq[%0d]=%0d",i,q[i]);
//     $display("\tq[2]=%0d",q[2]);

    q.push_back(8);//new element wii be discared
    $display("\tqueue elements: %0p",q);
    
  end
endmodule
```
    
    
