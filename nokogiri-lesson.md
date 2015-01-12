# Create a brand new Rails app
- You can follow instructions here: https://github.com/HK-WDI-November-2014/rails-basic-template
- Push to Github
- Push to Heroku
- Send the links to Harry's hipchat

# Get Kimono
1. Check out https://www.kimonolabs.com/
2. Sign up for an account
3. Install Kimono Chrome extension: https://chrome.google.com/webstore/detail/kimono/deoaddaobnieaecelinfdllcgdehimih?hl=en
4. Use the Kimono chrome extension to scrape a website
5. Use its tools to get matching html elements
	- screenshots

# Add `nokogiri` gem to Rails app
1. `gem 'nokogiri'`
2. Install library with `bundle install`

# Creating a rake task
- https://github.com/HK-WDI-November-2014/student-course-everything/issues/37
1. First create a `task_file_name.rake` file in `lib/tasks` folder. (eg. scrape.rake)
2. Template for a Rails rake job:

```ruby
namespace :task_file_name do
  # this is a description of your task
  desc "Task Description Here"

  # this is your task function
  task :task_name => :environment do
    # do something
  end
end
```

For example, you can do the following
```
namespace :scrape do
  desc “Scrape Google Finance Fundamentals”
  task :google_finance => :environment do
		puts “hello world!”
  end
end
```

# Access a website
- Add the following code snippets inside your task function
```ruby
require 'open-uri'

url = "http://www.google.com"
document = open(url).read
puts document
```

# Parsing with Nokogiri
```ruby
html_doc = Nokogiri::HTML(document)

	# columns
puts html_doc.css("div.id-incannualdiv > table.gf-table.rgt > tbody > tr > td.lft.lm").text
puts html_doc.css("div.id-incannualdiv > table.gf-table.rgt > tbody > tr > td:nth-child(2).r").text
puts html_doc.css("div.id-incannualdiv > table.gf-table.rgt > tbody > tr > td:nth-child(3).r").text
puts html_doc.css("div.id-incannualdiv > table.gf-table.rgt > tbody > tr > td:nth-child(4).r").text
puts html_doc.css("div.id-incannualdiv > table.gf-table.rgt > tbody > tr > td.r.rm").text
```

# Storing data
1. Create migration files and models to change database
- rails g model company
- rails g model annualincome
2. Store data from the task file

# Displaying data
1. Create views to index and show company
