# PL_SQL_Cursor

What are Cursors?
-----

A cursor is a temporary work area created in the system memory when a SQL statement is executed. A cursor contains information on a select statement and the rows of data accessed by it.


Implicit cursors
-----

These are created by default when DML statements like, INSERT, UPDATE, and DELETE statements are executed. They are also created when a SELECT statement that returns just one row is executed.

%FOUND, The return value is TRUE or FALSE

%NOTFOUND, The return value is TRUE or FALSE

%ROWCOUNT, Return the number of rows affected by the DML

%ISOPEN, The return value is TRUE or FALSE


Explicit Cursors
------

An explicit cursor is defined in the declaration section of the PL/SQL Block. It is created on a SELECT Statement which returns more than one row. We can provide a suitable name for the cursor

How to access an Explicit Cursor 
----
 
1) Open the cursor.

2) Fetch the records in the cursor one at a time.

3) Close the cursor.


 
       General Form of using an explicit cursor is:

        DECLARE
           variables;
           records;
           CURSOR cursor_name IS select_statement;
        BEGIN 
          OPEN cursor;
          FETCH cursor;
            process the records;
          CLOSE cursor;
        END;

 
LOOP
----
1. Simple Loop

LOOP 
   statements; 
   EXIT; 
   {or EXIT WHEN condition;}
END LOOP; 


2. FOR LOOP:

FOR record_name IN cusror_name 
LOOP 
    process the row...
END LOOP; 

3. While LOOP

WHILE <condition> 
 LOOP statements; 
END LOOP; 
 
 Example
 ----
 

     DECLARE 
      CURSOR emp_cur IS 
      SELECT first_name, last_name, salary FROM emp_tbl; 
     emp_rec emp_cur%rowtype; 
     BEGIN 
     FOR emp_rec in sales_cur 
     LOOP  
      dbms_output.put_line(emp_cur.first_name || ' ' ||emp_cur.last_name 
        || ' ' ||emp_cur.salary);  
     END LOOP; 
    END;
     /
