	
#### 멕시코보다 인구가 많은 나라이름과 인구수를 조회후, 인구수 순으로 내림차순 정리
```SQL
use world;

select name ,population
from country
order by population DESC
limit 0,10;
```


#### 국가별 몇개의 도시가 있는지 조회하고 도시수 순으로 10위까지 내림차순 정렬

```SQL
select country.name, count(city.countrycode) as count
from city
join country
on city.countrycode = country.code
group by country.name
order by count DESC
limit 0,10;
```
#### 언어별 사용인구를 출력하고 사용인구 순으로 10위까지 내림차순
**언어별 퍼센트가 있어서 계산후 합산 했었어야 함**

```SQL
select countrylanguage.Language,  round(sum(country.population * countrylanguage.Percentage)) as count
from countrylanguage
join country
on country.Code = countrylanguage.CountryCode
group by countrylanguage.Language
order by count DESC
limit 0,10;
```


#### 나라 전체 인구의 10% 이상인 도시에서 도시인구가 500만이 넘는 도시를 아래와 같이 조사 

```SQL
select city.name, city.countrycode, country.name, round((city.population / country.population * 100),2) as percentage
from country
join (
	select name,countrycode, population
	from city
	where population >= 5000000) as city
on city.countrycode = country.code
order by percentage DESC
limit 0,6;
```
#### 면적이 10000km^2이상인 국가의 인구밀도(1km^2당 인구수)를 구하고 인구밀도가 200이상인 국가들이 사용하고 있는 언어수가 5가지 이상인 라라를 조회하세요.

```SQL
select name, count(language) as language_count
from countrylanguage
join (

	select country.code, country.name, round((country.population /surfacearea.SurfaceArea)) as density
	from country
		join (
			select code, name, surfacearea
			from country
			where surfacearea > 10000) as surfacearea
			
	on country.code = surfacearea.code
	having density >= 200
	order by density DESC) as test

on test.code = countrylanguage.countrycode
group by name
having language_count >= 5
order by language_count DESC;
```
#### 가장 돈을 많이 지불한 상위 5명의 고객의 이름과 지불 금액 출력
```SQL
select customer.customer_id,concat(customer.first_name,' ',customer.last_name) as full_name,sum(payment.amount) as amount
from customer
join payment
on payment.customer_id = customer.customer_id
group by customer.customer_id
order by amount DESC
limit 0,5;
```
#### 배우별 영화 출연 횟수 출력 (상위 10개)
> - 컬럼: 배우이름, 출연횟수
> - 출연횟수 순으로 내림차순
```SQL
select actor.actor_id, concat(actor.first_name, ' ', actor.last_name) as full_name, count(concat(actor.first_name, ' ', actor.last_name)) as count
from actor
join film_actor
on actor.actor_id = film_actor.actor_id
group by actor.actor_id
order by count DESC, full_name
limit 0,10;
```
#### 영화 카테고리별 수입 데이터를 내림차순으로 정렬
> payment,rental,inventory,film_category,category
```SQL
select merged_rental_id.name, sum(payment.amount) as total_amount
from payment
join
		(select rental.rental_id, merged_inventory_id.name
		from rental
		join
				(select inventory.inventory_id, inventory.film_id, merged_film_id.name
				from inventory
				join (
						select category.category_id, category.name, film_category.film_id
						from category
						join film_category
						on category.category_id = film_category.category_id) as merged_film_id
						# as에서 지정해준 이름으로 안의 컬럼을 찾아 들어간다
				on inventory.film_id = merged_film_id.film_id) as merged_inventory_id
		on merged_inventory_id.inventory_id = rental.inventory_id) as merged_rental_id
on merged_rental_id.rental_id = payment.rental_id
group by name
order by total_amount DESC
limit 0,11;
```