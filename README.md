# <i><b><p align="center">MYSql:  Upgrad Graded Questions.. Module: Advanced SQL and Best Practices</p></b></i>


<img src="https://cdn.upgrad.com/UpGrad/temp/621d6a00-d119-4c93-b945-b7c9052a2a7b/sakila.png" >

## <b><p align="center">Graded Questions - I</p></b>


Q1: Most Productive Month Description Write a query to find the month number (Eg: 4 corresponds to April) in which the most number of payments were made. <br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165419223-76c0c851-7c4a-44da-b1d6-f33d8e8f7d62.png">
Sol:  <p>use upgrad;<br>
      Select month(payment_date) as mth;<br>
                count(payment_id) as pay;<br>
      from payment group by mth;<br>
      order by pay desc limit 1;</p>

Q2: ## Average Film Length by Category<br>
Description:<br>
List the rounded average film lengths for each film category. Arrange the values in the decreasing order of the average film lengths.<br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165419575-5c1bc5ad-c783-4ecd-9460-3696866cae0e.png">
Sol:<p>use upgrad;<br>
      select round(avg(f.length)) as avg_Length, c.name as name from film f, category c, film_category fc;<br>
      where c.category_id=fc.category_id and fc.film_id=f.film_id;
      group by c.name;
      order by avg_Length desc;</p>















## Graded Questions - II
