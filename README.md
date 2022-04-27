##  <i><b><p align="center">MYSql:  Upgrad Graded Questions.. Module: Advanced SQL and Best Practices</p></b></i>


<img src="https://cdn.upgrad.com/UpGrad/temp/621d6a00-d119-4c93-b945-b7c9052a2a7b/sakila.png" >

## <b><p align="center">Graded Questions</p></b>


Q1: Most Productive Month Description Write a query to find the month number (Eg: 4 corresponds to April) in which the most number of payments were made.
Sol:  <p>use upgrad;<br>
      Select month(payment_date) as mth;<br>
                count(payment_id) as pay;<br>
      from payment group by mth;<br>
      order by pay desc limit 1;</p>

Q2: 
