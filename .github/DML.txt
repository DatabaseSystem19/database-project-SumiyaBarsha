INSERT INTO cashier VALUES (1, 'John Doe', 25, 3000);
INSERT INTO cashier VALUES (2, 'Jane Smith', 30, 3500);
INSERT INTO cashier VALUES (3, 'Mike Johnson', 28, 3200);
INSERT INTO cashier VALUES (4, 'John Doe', 34, 3400);
INSERT INTO cashier VALUES (5, 'Fernando Edwards', 30, 3500);
INSERT INTO cashier VALUES (6, 'Christine Maxwell', 27, 3000);
INSERT INTO cashier VALUES (7, 'Joyce West', 24, 3200);
INSERT INTO cashier VALUES (8, 'James Millman', 31, 2800);
INSERT INTO cashier VALUES (9, 'Patricia Young', 28, 3600);
INSERT INTO cashier VALUES (10, 'Bruce Morris', 22, 3000);

INSERT INTO customer VALUES (1, 'Alice Brown', 'Female', 1234567890, 'alice@example.com');
INSERT INTO customer VALUES (2, 'Bob Smith', 'Male', 9876543210, 'bob@example.com');
INSERT INTO customer VALUES (3, 'Charlie Davis', 'Male', 5678901234, 'charlie@example.com');
INSERT INTO customer VALUES (4, 'Walter Rouse', 'Male', 2187888989, 'walter@example.com');
INSERT INTO customer VALUES (5, 'Lisa Phelps', 'Female', 9897147788, 'lisa@example.com');
INSERT INTO customer VALUES (6, 'Rebecca Reye', 'Female',3362611166 , 'reye@example.com');
INSERT INTO customer VALUES (7, 'Rebecca Corbett', 'Female',8889895678 , 'corbett@example.com');
INSERT INTO customer VALUES (8, 'William Diaz', 'Male',7890147283 , 'william@example.com');
INSERT INTO customer VALUES (9, 'Ivory Hudson', 'Male', 8088283401, 'ivory@example.com');
INSERT INTO customer VALUES (10, 'Sheila Smith', 'Female', 3054623647, 'sheila@example.com');


INSERT INTO movie VALUES (1, 'The Avengers', 'English', 150, 'Action', 300, DATE '2022-05-15');
INSERT INTO movie VALUES (2, 'Dub', 'Bangla', 148, 'Thriller', 250, DATE '2010-07-16');
INSERT INTO movie VALUES (3, 'Frozen', 'English', 102, 'Animation', 280, DATE '2013-11-27');
INSERT INTO movie VALUES (4, 'Television', 'Bangla', 160, 'Comedy', 280, DATE '2014-07-14');
INSERT INTO movie VALUES (5, 'Pride and Prejudice', 'English', 200, 'Romance', 250, DATE '2002-01-16');
INSERT INTO movie VALUES (6, 'Farha', 'Arabic', 110, 'Thriller', 200, DATE '2013-10-20');
INSERT INTO movie VALUES (7, 'Sputnik', 'Russian', 154, 'Action', 350, DATE '2008-05-08');
INSERT INTO movie VALUES (8, 'A Whisker Away', 'Japanese', 128, 'Animation', 250, DATE '2022-09-10');
INSERT INTO movie VALUES (9, 'Devdas', 'Hindi', 102, 'Drama', 400, DATE '2000-11-13');
INSERT INTO movie VALUES (10, 'Your Name', 'Japanese', 148, 'Animation', 300, DATE '2017-04-10');


INSERT INTO booking VALUES(1, 2, 1, 1, TO_DATE( '2023-05-21 15:00:00', 'YYYY-MM-DD HH24:MI:SS'), 4, 1);
INSERT INTO booking VALUES(2, 3, 2, 2, TO_DATE ('2023-05-22 18:30:00', 'YYYY-MM-DD HH24:MI:SS'), 5, 2);
INSERT INTO booking VALUES(3, 1, 10, 3, TO_DATE ('2023-05-23 14:45:00', 'YYYY-MM-DD HH24:MI:SS'), 1, 3);
INSERT INTO booking VALUES(4, 2, 4, 1, TO_DATE ('2023-05-24 10:15:00', 'YYYY-MM-DD HH24:MI:SS'), 4, 8);
INSERT INTO booking VALUES(5, 4, 7, 2, TO_DATE ('2023-05-25 19:00:00', 'YYYY-MM-DD HH24:MI:SS'), 6, 4);
INSERT INTO booking VALUES(6, 3, 5, 3, TO_DATE ('2023-05-26 16:30:00', 'YYYY-MM-DD HH24:MI:SS'), 10, 2);
INSERT INTO booking VALUES(7, 2, 2, 1, TO_DATE ('2023-05-27 17:45:00', 'YYYY-MM-DD HH24:MI:SS'), 1, 4);
INSERT INTO booking VALUES(8, 5, 8, 2, TO_DATE ('2023-05-28 14:00:00', 'YYYY-MM-DD HH24:MI:SS'), 2, 5);
INSERT INTO booking VALUES(9, 3, 4, 3, TO_DATE ('2023-05-29 18:00:00', 'YYYY-MM-DD HH24:MI:SS'), 2, 10);
INSERT INTO booking VALUES(10, 1, 5, 1, TO_DATE ('2023-05-30 12:30:00', 'YYYY-MM-DD HH24:MI:SS'), 9, 7);



INSERT INTO payment VALUES (1, TO_DATE('2023-05-21 15:30:00', 'YYYY-MM-DD HH24:MI:SS'), 1);
INSERT INTO payment VALUES (2, TO_DATE('2023-05-22 18:45:00', 'YYYY-MM-DD HH24:MI:SS'), 2);
INSERT INTO payment VALUES (3, TO_DATE('2023-05-23 16:15:00', 'YYYY-MM-DD HH24:MI:SS'), 3);
INSERT INTO payment VALUES (4, TO_DATE('2023-05-24 11:00:00', 'YYYY-MM-DD HH24:MI:SS'), 8);
INSERT INTO payment VALUES (5, TO_DATE('2023-05-25 19:30:00', 'YYYY-MM-DD HH24:MI:SS'), 4);
INSERT INTO payment VALUES (6, TO_DATE('2023-05-26 17:45:00', 'YYYY-MM-DD HH24:MI:SS'), 2);
INSERT INTO payment VALUES (7, TO_DATE('2023-05-27 18:00:00', 'YYYY-MM-DD HH24:MI:SS'), 4);
INSERT INTO payment VALUES (8, TO_DATE('2023-05-28 15:15:00', 'YYYY-MM-DD HH24:MI:SS'), 5);
INSERT INTO payment VALUES (9, TO_DATE('2023-05-29 19:30:00', 'YYYY-MM-DD HH24:MI:SS'), 10);
INSERT INTO payment VALUES (10, TO_DATE('2023-05-30 20:45:00', 'YYYY-MM-DD HH24:MI:SS'), 7);








/*Checking the existing table in database*/

select table_name from user_tables;



/*Updating a value in cashier table*/

update cashier set salary=3000 where cashier_name ='Joyce West';


/*calculate salary with 10% bonus for each cashier*/
select cashier_id,cashier_name,age,(salary*1.1) as tot_salary
from cashier; 


/*deleting row from table*/

INSERT INTO customer VALUES (11, 'Sana Smith', 'Female', 3054624657, 'sana@example.com');
delete from customer where customer_id=11;


/*search salary range*/


select cashier_id,cashier_name,salary from cashier
where salary>=3000 and salary<=3500;


/*search specific order in name*/

select customer_name 
from customer 
where customer_name like '%li%';


/*search female customers information*/

select * from customer
where gender='Female';


/*find the movies released before 20 OCTOBER 2013*/

select *
from movie
where release_date < date '2013-10-20';



/*movie ordered by decreasing ticket_price */

select * 
from movie
order by ticket_price desc;


/*find total entry,total salary,maximum salary,minimum salary,average salary of the cashier */
select count(*) as no_of_entry,
max(salary) as max_sal,
min(salary) as min_sal,
avg(salary) as avg_sal,
sum(salary) as tot_sal
from cashier;


/*find distinct movie language*/

select distinct(language) from movie;


/*find total number of movies of distinct language using group by*/

select count(movie_id) as tot_movie,language
from movie
group by language; 


/*find those movies where the average length of the movies is more than 130 using having*/

select genre,avg(length_min) as avg_length
from movie
group by genre
having avg(length_min)>130; 


/*find movie information which released after May,2008 and is of animation genre*/

select * from movie
where release_date > date '2008-05-01'
union
select * from movie
where genre ='animation';


/*find booking information which made after 23 May,2023 and is done by cashier named Jane Smith*/

select * from booking
where booking_dt > date '2023-05-23'
intersect 
select * from booking 
where cashier_id = ( select cashier_id
from cashier where cashier_name = 'Jane Smith');


/*find movie which is English but not action*/

(select movie_id,movie_name
from movie
where language like '%English%')
minus
(select movie_id,movie_name
from movie
where genre like '%Action%');



/*Find the movie name Ivory Hudson paid to watch*/

select movie_name from movie
where movie_id = (select movie_id from booking
where customer_id = (select customer_id from customer
where customer_name = 'Ivory Hudson'));


/*Find customer  whose mobile has '88' string in it and is female*/

select customer_name,email_id from customer where mobile like '%88%' 
and customer_id in (select customer_id from customer where gender = 'Female');


/*Find customer  whose mobile has '88' string in it or is female*/

select customer_name,email_id from customer where mobile like '%88%' 
or customer_id in (select customer_id from customer where gender = 'Female');


/*Find customer  whose mobile has '88' string in it but not  female*/

select customer_name,email_id from customer where mobile like '%88%' 
or customer_id in (select customer_id from customer where gender = 'Female');


/*Find the maximum value of ticket price from table movie  using with clause*/

with max_price(val) as (select max(ticket_price) from movie)
select * from movie,max_price where movie.ticket_price = max_price.val;



/*Find booking information of theatre 2 which is booked by cashier aged equal or more than 27*/

select * from booking where theatre_id = 2 and exists (select cashier_id from cashier where age >= 27);


/*Natural Join*/
select * from cashier natural join booking where cashier_id=7;

select cashier_id ,movie_id from cashier join booking using(cashier_id);

select cashier_id ,movie_id from cashier left outer join booking using(cashier_id);
select cashier_id ,movie_id from cashier right outer join booking using(cashier_id);
select cashier_id ,movie_id from cashier full outer join booking using(cashier_id);


/*Find all movies booked by customer id 4 */
create view Movies_Booked as select movie_id from movie where movie_id=(select movie_id from customer where customer_id=4);



/*find movie id and booking date where booking made by customer whose id is greater than 2 but customer is not female*/

 
select movie_id, c.customer_id,booking_dt as booking_date,
to_char(booking_dt,'hh24:mm:ss') as booking_time
from booking b
join customer c on c.customer_id= b.customer_id
where gender !='Female' and c.customer_id >2; 







