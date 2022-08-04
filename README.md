# <i><b><p align="center" font="30px">Module: Advanced SQL and Best Practices</p></b></i>


<img src="https://cdn.upgrad.com/UpGrad/temp/621d6a00-d119-4c93-b945-b7c9052a2a7b/sakila.png" >

## <b><p align="center">Graded Questions - I</p></b>


### Q1: Most Productive Month Description Write a query to find the month number (Eg: 4 corresponds to April) in which the most number of payments were made. <br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165419223-76c0c851-7c4a-44da-b1d6-f33d8e8f7d62.png"><br>
Sol:  <p>use upgrad;<br>
      Select month(payment_date) as mth<br>
                count(payment_id) as pay<br>
      from payment group by mth<br>
      order by pay desc limit 1</p>
<br>
### Q2: Average Film Length by Category<br>
Description:<br>
List the rounded average film lengths for each film category. Arrange the values in the decreasing order of the average film lengths.<br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165419575-5c1bc5ad-c783-4ecd-9460-3696866cae0e.png"> <br>
Sol:<p>use upgrad;<br>
      select round(avg(f.length)) as avg_Length, c.name as name from film f, category c, film_category fc<br>
      where c.category_id=fc.category_id and fc.film_id=f.film_id<br>
      group by c.name<br>
      order by avg_Length desc;</p>
<br><br>

## <p align="center"> Graded Questions - II</p>

### Q1: Film Category vs. City<br>
Description:<br>
Write a query to find the number of occurrences of each film_category in each city. Arrange them in the decreasing order of their category count.<br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165420167-f526b220-5cb2-4817-975e-6d51834672cf.png"> <br>
Sol: <p> use upgrad;<br>
SELECT name, city, COUNT(category_id) AS category_count FROM category;<br> 
      INNER JOIN film_category<br> USING (category_id) INNER JOIN inventory USING(film_id) 
      <br>INNER JOIN store USING (store_id) INNER JOIN address USING (address_id) INNER JOIN city USING (city_id) <br>
      GROUP BY name, city <br>
      ORDER BY category_count DESC;  </p>

## Q2: Ad Campaign
Description: <br>
Suppose you are running an advertising campaign in Canada for which you need the film_ids and titles of all the films released in Canada. List the films in the alphabetical order of their titles. <br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165420986-1d6467c2-92ba-4415-820d-7d0a1e872941.png"><br>
Sol: <p> use upgrad;<br>
      select Film_id, Title from film inner join inventory using (film_id) <br>
      inner join store using (store_id) inner join address using (address_id)<br>
      inner join city using (city_id) inner join country using (country_id) <br>
      where country = 'Canada' <br>
      group by film_id, title <br>
      order by title;</p>
      
## Q3: Comedy Movies
Description: <br>
Write a query to list all the films existing in the 'Comedy' category and arrange them in the alphabetical order.<br>
Sample Output:<br>
<p>title<br>
ACADEMY DINOSAUR</p>
Sol: <p> use upgrad;<br>
      select Title<br>
      from film <br>
      inner join film_category<br>
      using (film_id)<br>
      inner join category<br>
      using (category_id)<br>
      where name = 'Comedy'<br>
      order by title;<br></p>
      
## Q4: Lucky Customers
Description:<br>
List the first and last names of all customers whose first names start with the letters 'A', 'J' or 'T' or last names end with the substring 'on'. Arrange them alphabetically in the order of their first names.<br>
Sample Output:<br>
<img src="https://user-images.githubusercontent.com/102786084/165422597-b400275d-3b67-4033-8b7a-a88101651db9.png"> <br>
Sol: <p>use upgrad;<br>
      select First_name, Last_name<br>
      from customer<br>
      where first_name regexp '^[ajt]' or last_name regexp 'on$'<br>
      order by first_name; </p>


# <p align="center" fomt="30px"> 😊:THANK YOU:😊 </P>
 
