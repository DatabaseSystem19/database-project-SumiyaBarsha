/*PL/SQL*/

/*count row for table payment using pl/sql*/

set serveroutput on
declare 
cursor payment_cursor is select * from payment;
payment_row payment%rowtype;
begin
open payment_cursor;
fetch payment_cursor into payment_row.payment_id,payment_row.pay_dt,payment_row.customer_id;
while payment_cursor%found loop
dbms_output.put_line('Payment_id: '||payment_row.payment_id|| ' Payment_Date: '||payment_row.pay_dt || ' Customer_Id: '||payment_row.customer_id);
dbms_output.put_line('Row count: '|| payment_cursor%rowcount);
fetch payment_cursor into payment_row.payment_id,payment_row.pay_dt,payment_row.customer_id;
end loop;
close payment_cursor;
end;
/







/*FOR LOOP/WHILE LOOP/ARRAY with extend() function*/

set serveroutput on
declare 
  counter number;
  customer_name2 customer.customer_name%type;
  TYPE NAMEARRAY IS VARRAY(10) OF customer.customer_name%type; 
  A_NAME NAMEARRAY:=NAMEARRAY();
begin
  counter:=1;
  for x in 1..10  
  loop
    select customer_name into customer_name2 from customer where customer_id =x;
    A_NAME.EXTEND();
    A_NAME(counter):=customer_name2;
    counter:=counter+1;
  end loop;
  counter:=1;
  WHILE counter<=A_NAME.COUNT 
    LOOP 
    DBMS_OUTPUT.PUT_LINE(A_NAME(counter)); 
    counter:=counter+1;
  END LOOP;
end;
/



/*ARRAY without extend() function*/

DECLARE 
   counter NUMBER := 1;
   customer_name2 customer.customer_name%TYPE;
   TYPE NAMEARRAY IS VARRAY(10) OF customer.customer_name%TYPE;
   A_NAME NAMEARRAY:=NAMEARRAY('customer 1', 'customer 2', 'customer 3', 'customer 4', 'customer 5','customer 6', 'customer 7', 'customer 8', 'customer 9', 'customer 10'); 
   -- VARRAY with a fixed size of 10 elements and initialized with customer names
BEGIN
   counter := 1;
   FOR x IN 1..10  
   LOOP
      SELECT customer_name INTO customer_name2 FROM customer WHERE customer_id=x;
      A_NAME(counter) := customer_name2;
      counter := counter + 1;
   END LOOP;
   counter := 1;
   WHILE counter <= A_NAME.COUNT 
   LOOP 
      DBMS_OUTPUT.PUT_LINE(A_NAME(counter)); 
      counter := counter + 1;
   END LOOP;
END;
/




/*IF /ELSEIF /ELSE*/

DECLARE 
   counter NUMBER := 1;
   movie_name2 movie.movie_name%TYPE;
   TYPE NAMEARRAY IS VARRAY(6) OF movie.movie_name%TYPE;
   A_NAME NAMEARRAY:=NAMEARRAY('movie 1', 'movie 2', 'movie 3', 'movie 4', 'movie 5','movie 6'); 
   -- VARRAY with a fixed size of 6 elements and initialized with movie names
BEGIN
   counter := 1;
   FOR x IN 1..6
   LOOP
      SELECT movie_name INTO movie_name2 FROM movie WHERE movie_id=x;
      if movie_name2='The Avengers' 
        then
        dbms_output.put_line(movie_name2||' is an '||'English movie');
      elsif movie_name2='Frozen' 
        then
        dbms_output.put_line(movie_name2||' is an '||'English movie');
      elsif movie_name2='Pride and Prejudice' 
        then
        dbms_output.put_line(movie_name2||' is an '||'English movie');
      elsif movie_name2='Dub'  
        then
        dbms_output.put_line(movie_name2||' is a '||'Bangla Movie');
 elsif movie_name2='Television'  
        then
        dbms_output.put_line(movie_name2||' is a '||'Bangla Movie');
      else 
        dbms_output.put_line(movie_name2||' is a '||'others');
        end if;
   END LOOP;
END;
/



/*Procedure*/

/* select language, ticket price and booking information of  movie id = 10 */

set  serveroutput on
create or replace procedure get_movie_info(
id in movie.movie_id%type) is

mid movie.movie_id%type := id ;
cursor movie_cur is select * from movie natural join booking where movie_id=mid;
movie_record movie_cur%rowtype;

begin
open movie_cur;
loop
fetch movie_cur into movie_record;
exit when movie_cur%notfound;
if movie_record.movie_id=10 then
dbms_output.put_line ('id: ' || movie_record.movie_id || '  movie_name:' ||movie_record.movie_name|| ' ticket_price: '||movie_record.ticket_price||' booked by: '||
movie_record.customer_id||' date : '||movie_record.booking_dt);
end if;

end loop;
 close movie_cur;
end get_movie_info;
/

begin
get_movie_info(1);
end;
/

/*Function*/

/*calculate annual salary of cashiers with 25% annual commission*/
set serveroutput on

create or replace function get_annual_salary(
sal in cashier.salary%type,
comm in cashier.salary%type)
return number is
begin
return (nvl(sal,0) * 12 + (nvl(comm,0) * nvl(sal,0) * 12));
end get_annual_salary;
/

select cashier_id, cashier_name,age,salary,
get_annual_salary(salary, 0.25) "Annual
Compensation"
from cashier;
/


/*drop procedure and function*/
drop procedure get_movie_info;
drop function get_annual_salary;





