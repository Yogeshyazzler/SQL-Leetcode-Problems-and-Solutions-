## SQL Advanced 50 Problems:

1)Write a solution to find the ids of products that are both low fat and recyclable.
Solution - select product_id from Products where low_fats = 'Y' and recyclable = 'Y';

2)Find all numbers that appear at least three times consecutively.
Solution -

 with cte as 
(select num,
       lead(num,1) over() num1,
       lead(num,2) over() num2
       from
       Logs)

select distinct num as ConsecutiveNums from cte where num= num1 and num1=num2;


