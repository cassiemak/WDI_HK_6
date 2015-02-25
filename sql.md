```ruby
query = 
"
SELECT COUNT(recipes_id) AS count_all, new.recipes_id AS recipes_id
FROM
(
SELECT DISTINCT recipes.id AS recipes_id 
FROM recipes

INNER JOIN recipe_ingredient_lists 
ON recipes.id=recipe_ingredient_lists.recipe_id 

WHERE recipe_ingredient_lists.ingredient_id=3

GROUP BY recipes_id

UNION ALL

SELECT DISTINCT recipes.id AS recipes_id 
FROM recipes

INNER JOIN recipe_ingredient_lists 
ON recipes.id=recipe_ingredient_lists.recipe_id 

WHERE recipe_ingredient_lists.ingredient_id=2

UNION ALL

SELECT DISTINCT recipes.id AS recipes_id 
FROM recipes

INNER JOIN recipe_ingredient_lists 
ON recipes.id=recipe_ingredient_lists.recipe_id 

WHERE recipe_ingredient_lists.ingredient_id=5

) AS new

GROUP BY recipes_id

HAVING COUNT(*) > 2

LIMIT 10;

"

ActiveRecord::Base.connection.execute(query).each do |row|
  # id = row['recipes_id']
  # puts row
  # puts Recipe.find(id).ingredients.where(:id => 23).any? and Recipe.find(id).ingredients.where(:id => 32).any?

  puts row

  # array = []
  # if row['count_all'].to_i == 3
  # 	array << row['recipes_id']
  # end
  # puts array
end

```

```ruby
# get all recipes in Rails
Recipe.all.limit(10)
# get all recipes in SQL
sql = "SELECT * FROM recipes LIMIT 10"



# in rails
Recipe.where(:name => "chicken").limit(10)
# in sql
sql = "SELECT * FROM recipes WHERE name='chicken' LIMIT 10"

# rails
Recipe.where("name LIKE '%Pie%'").limit(10)
# in sql
sql = "SELECT * FROM recipes WHERE name LIKE '%Pie%' LIMIT 10"

# select first 3 recipes and get all the integrients of these recipes
# rails
Recipe.first(3).each do |recipe|
	puts recipe.ingredients.count
end

Recipe.all.includes(:recipe_category_lists)

y User.all.includes(:likes).take(2)
# in sql
sql = "
SELECT *

FROM users 

INNER JOIN likes 

ON users.id = likes.user_id

LIMIT 2"

ActiveRecord::Base.connection.execute(sql).each do |item|
  y item
end

# in controller
@users = User.where("id < 10000") # 10000 records
@users = User.where("id < 10000").includes(:likes) # 1 query -> 50ms

# in view / html
# display all likes
# 10000 times of SQL query -> 2 minutes
<% @users.each do |user| %>
	<%= user.likes.count %>
<% end %>


```
