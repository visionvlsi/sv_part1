#### structure and union

#### Example-1 
```
//-------------------without typedef-----------------
module struct_example;
  struct {
    string name;
    bit[31:0] salary;
    integer id;
  } employee;
    
  initial begin
    employee.name = "Alex";
    employee.salary = 'h10000;
    employee.id     = 'd1234;
    $display("employee: %p", employee);
    
    // Accessing individual struct member
    $display("employee: name = %s, salary = 0x%0h, id = %0d", employee.name, employee.salary, employee.id);
  end
endmodule
```
#### Example-2
```
//----------------------------with tytpedef------------------
module struct_example;
  typedef struct {
    string name;
    bit[31:0] salary;
    integer id;
  } employee;
    
  initial begin
    employee e1, e2;
    e1.name = "Alex";
    e1.salary = 'h10000;
    e1.id     = 'd1234;
    $display("employee e1: %p", e1);
    
    e2.name = "Bob";
    e2.salary = 'h20000;
    e2.id     = 'd4321;
    $display("employee e2: %p", e2);
    $display("-------------------------------------------------");
    
    // Accessing individual struct member
    $display("employee e1: name = %s, salary = 0x%0h, id = %0d", e1.name, e1.salary, e1.id);
    $display("employee e2: name = %s, salary = 0x%0h, id = %0d", e2.name, e2.salary, e2.id);
  end
endmodule
```
#### Example-3
```
//--------------packed structure----------------------------------
module struct_example;
  typedef struct packed {
    
    bit[31:0] salary;
    integer id;
 
  } employee;
    
  initial begin
    employee emp1, emp2;
    emp1.salary = 'h10000;
    emp1.id     = 'd1234;
    $display("EMP 1: %p", emp1);
    
    emp2.salary = 'h12000;
    emp2.id     = 'd4321;
    $display("EMP 2: %p", emp2);
  end
endmodule
```
#### Example-4
```
//--------------------------un packed structure-------------------------
module struct_example;
  typedef struct   {
    string name;
    bit[31:0] salary;
    integer id;
  } employee;
    
  initial begin
    employee emp1, emp2;
    emp1.name = "Alex";
    emp1.salary = 'h10000;
    emp1.id     = 'd1234;
    $display("EMP 1: %p", emp1);
    
    emp2.name = "John";
    emp2.salary = 'h12000;
    emp2.id     = 'd4321;
    $display("EMP 2: %p", emp2);
  end
endmodule
```
#### Example-5
```
//----------------------passign structure in a function/task----------------------
module struct_example;
  
  typedef struct {
    string name;
    bit[31:0] salary;
    integer id;
  } employee;
    
  function void print_struct(employee emp);
    $display("EMP: %p", emp);
  endfunction
  
  function employee create_struct(string name, bit [31:0] salary, integer id);
    employee emp;
    emp.name = name;
    emp.salary = salary;
    emp.id     = id;
    return emp;
  endfunction
  
  initial begin
    employee emp1, emp2;
    emp1 = create_struct("Alex",'h10000, 'd1234);
    emp2 = create_struct("John",'h12000, 'd4321);
    print_struct(emp1);
    print_struct(emp2);
  end
endmodule
```
