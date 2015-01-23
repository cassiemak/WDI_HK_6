1.	Install Angularjs through Gemfile. Add the following to your `Gemfile`
```ruby
gem 'angularjs-rails'
```
2.	`bundle install` in terminal
3.	In application.js, and the line of `//= require angular` just before `//= require_tree .`
4. Remember to remove turbolinks
5.	In `application.html.erb`, add `ng-app` to the `<html>` tag as an attribute
6.
  - Copy the first example code from official site to our application
  - Copy the `<input type="text" ng-model="yourName" placeholder="Enter a name here">`
  - Copy the `<h1>Hello {{yourName}}!</h1>`
7.	Refresh the page, the input field comes out, try it out!!
8.	Visit https://angularjs.org/, try the examples on the home page
