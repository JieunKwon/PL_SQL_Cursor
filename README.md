# PL_SQL_Cursor

How to access an Explicit Cursor?
These are the three steps in accessing the cursor.
1) Open the cursor.
2) Fetch the records in the cursor one at a time.
3) Close the cursor.


General Form of using an explicit cursor is:
 DECLARE
    variables;
    records;
    create a cursor;
 BEGIN 
   OPEN cursor;
   FETCH cursor;
     process the records;
   CLOSE cursor;
 END;
 
 

General Syntax for using FOR LOOP:

FOR record_name IN cusror_name 
LOOP 
    process the row...
END LOOP; 


1> DECLARE 
2>  CURSOR emp_cur IS 
3>  SELECT first_name, last_name, salary FROM emp_tbl; 
4>  emp_rec emp_cur%rowtype; 
5> BEGIN 
6>  FOR emp_rec in sales_cur 
7>  LOOP  
8>  dbms_output.put_line(emp_cur.first_name || ' ' ||emp_cur.last_name 
9>    || ' ' ||emp_cur.salary);  
10> END LOOP; 
11>END;
12> /
