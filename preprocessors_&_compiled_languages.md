# Preprocessors & Compiled Languages


### Key principles

* DRY!
* Beautiful code (well indented)
* Efficient code
* Code faster


## HTML Preprocessors

#### Slim

* Adapts well with Ruby
* Docs here: [Slim](http://slim-lang.com/)

        gem 'slim'
* Demo
* Let's try!


#### Other HTML Preprocessors

* [Emblem](http://emblemjs.com/)
* [HAML](http://haml.info/)
* [Jade](http://jade-lang.com/)




## CSS Preprocessors

**Key features:**

* Nested rules
* Nested properties
* Variables
* Functions
* Color operations
* Partials
* Mixins
...

#### SASS / SCSS

* [SASS](http://sass-lang.com/)
* Adapts well with Foundation

        gem 'sass-rails', '~> 4.0.3'

#### Stylus

* Preprocessor + Precompiled!
* [Stylus](http://learnboost.github.io/stylus/)


        gem 'stylus', '~> 1.0.1'

#### LESS

* [LESS](http://lesscss.org/)
* Adapts well with Bootstrap



I
## CoffeeScript: Compiles into JavaScript

Docs: [CoffeeScript.org](http://coffeescript.org/)

Learn with interactive book: [Smooth CoffeeScript](http://autotelicum.github.io/Smooth-CoffeeScript/)

Google Chrome Extension (Command+Enter or Shift+Enter to run the script you've typed in CoffeeConsole): [CoffeeConsole2](https://chrome.google.com/webstore/detail/coffeeconsole-2/kcdehbekjjicimoacajfpcpihajfnbfp?hl=en-US)

Add to Gemfile:

        gem 'coffee-script'

Install locally:

        $ npm install -g coffee-script

Create a file.coffee and try:

        console.log 'hello'
        
        myName = 'Paul'
        if myName is 'Paul' or 'Harry'
            console.log 'You\'re an instructor'
        else
            console.log 'You\'re a student'
            
        myList = 
            1
            3
            6
            9
            
        console.log 'myArray', myArray
        for i in myArray
            console.log i
        
        myKids =
            brother:
                name: "Max"
                age:  11
            sister:
                name: "Ida"
                age:  9
                
        countdown = (num for num in [10..1])
        


Compile one file: 

        $ coffee -c file.coffee
        
Compile on save + create a map file:
        
        $ coffee -cmw file.coffee

