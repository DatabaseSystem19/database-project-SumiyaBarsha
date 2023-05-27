drop table booking;
drop table payment;
drop table movie;
drop table customer;
drop table cashier;



create table cashier(
cashier_id int NOT NULL,
cashier_name varchar(20),
age int check (age >= 18),
salary int,
primary key(cashier_id)
);

create table customer(
customer_id int NOT NULL,
customer_name varchar(20) NOT NULL,
gender varchar(10),
mobile int NOT NULL,
email_id varchar(20) NOT NULL,
primary key(customer_id)
);

create table movie(
movie_id int NOT NULL,
movie_name varchar(50),
language varchar(10),
length_min int,
type varchar(20),
ticket_price int,
release_date date,
primary key(movie_id)
);

create table booking(
booking_id int NOT NULL,
no_of_ticket int,
movie_id int,
theatre_id int,
booking_dt date,
customer_id int,
cashier_id int,
primary key(booking_id),
foreign key(cashier_id) references cashier(cashier_id),
foreign key(movie_id) references movie(movie_id),
foreign key(customer_id) references customer(customer_id)
);

create table payment(
payment_id  int NOT NULL,
pay_dt date,
customer_id int NOT NULL,
primary key(payment_id),
foreign key(customer_id) references customer(customer_id)
);



/*Adding a new column to table payment*/

alter table payment add  amount int;
describe payment;


/*Modify column definition in the table*/

alter table movie modify movie_name varchar(40);
describe movie;

/*Rename the column name*/

alter table movie rename column type to genre;
describe movie;


/*Drop the column from table*/

alter table payment drop column amount;
describe payment;








