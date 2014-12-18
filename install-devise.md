# Adding Devise
1. add gem ‘devise’ in Gemfile
2. bundle install

### install necessary configs for devise
3. rails generate devise:install 

### this generate the recipe, or the migration file for users
4. rails g devise user

### to customize our login views
5. rails g devise:views

### cooking the recipe / running the migration
6. rake db:migrate
7. restart your server
8. go to http://localhost:3000/users/sign_in
9. go to http://localhost:3000/users/sign_up
10. Lets add the sign out button!
