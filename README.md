create database banks;
use banks;
create table employees(e_id int,
e_salary int check (e_salary>8000),
e_name varchar(20) not null,
branch_name varchar(20) not null,
branch_id varchar(10) primary key,
e_age int check(e_age>21));

insert into employees values(1,10000,"Rasi","Covai","B01",22),
(2,17000,"Gowsi","Chennai","B02",21),
(3,25000,"Venky","Bangalore","B03",25),
(4,35000,"Sanjay","Namakkal","B04",27),
(5,30000,"Naveen","Bangalore","B05",32),
(6,54000,"Pravin","Covai","B06",23),
(7,25000,"Yogi","Chennai","B07",30),
(8,10000,"Suriya","Namakkal","B08",29),
(9,9000,"Vickey","Bangalore","B09",23),
(10,20000,"Vasanth","Covai","B10",26);
select*from employees;

create table customer(c_accNo int not null,
c_pin int ,
c_name varchar(20) not null,
balance_amount int,
acc_type varchar(20),
c_panNo varchar(20) primary key,
c_contactNo varchar(10),
c_address varchar(50) default "not mention",
branch_id varchar(20));
select*from customer;

insert into customer values(1234567,2345,"Mathan",20000,"Savings_account","Math123","9807654321","Rasipuram","B01"),
(879765432,1234,"Dharan",30000,"Current_account","dhar123","9456987123","Madurai","B07"),
(987654321,2346,"Mohan",45500,"Savings_account","Mohan123","9780654321","Rasipuram","B04"),
(9790268777,9876,"Prem",56000,"Current_account","Prem567","7502333347","Erode","B06"),
(4567890432,5555,"Puviyan",58700,"Current_account","Puvi123","8976543120","Madras","B02"),
(9807564231,9870,"Mathumitha",30000,"Current_account","Mathu123","6578904321","Dharmapuri","B10"),
(6785430271,6308,"Sivanesh",65000,"Savings_account","Siva123","8907123456","Attur","B03"),
(5432178906,7896,"Sandhiya",78000,"Current_account","San123","9870645123","Gugai","B07"),
(7890456123,1111,"Pramoth",20000,"Savings_account","Pram103","6789065432","Valapady","B06"),
(8907651234,2222,"Selvakumar",45320,"Current_account","selva908","8698994567","Trichy","B04"),
(6579084321,3333,"Sangeetha",23000,"Savings_account","San123","9750081267","Attur","B10"),
(1234567890,4444,"Ramesh",80000,"Savings_account","Rames123","9586527126","Thammampatty","B05"),
(2345169870,5555,"Sudha",45000,"Current_account","Suda123","8907651234","Salem","B09"),
(5678901234,6666,"Priya",100000,"Savings_account","Pri997","9940406757","Rasipuram","B08"),
(3456789012,7777,"Kalaiselvi",160000,"Current_account","Kalai123","9551118866","Salem","B02");

select*from customer;

use bank;

select customer.c_accNo, customer.c_pin, customer.c_name, customer.balance_amount, customer.acc_type, customer.c_panNo, 
customer.c_contactNo, customer.c_address, employees.e_id, employees.e_salary, employees.e_name, employees.branch_name, employees.e_age
from customer
inner join employees
on employees.branch_id=customer.branch_id;
select*from customer order by branch_id;
