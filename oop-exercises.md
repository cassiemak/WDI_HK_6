// OOP Lesson
```ruby
# create a Ruby file with whatever name you pick and put it wherever you want

# puts "This file works"

# We are creating a prototype (blueprint) of an object. Objects are usually categorized

class Animal
  # For an objets, there are mandatory properties
  def initialize(name)
    puts "An animal has been created"

    # this code will take the 'name' and store it in the instance
    @name = name
  end

  # You can also define the functions of this object
  def eat
    puts "The animal is eating"
  end

  def drink
    puts "The animal is drinking"
  end

  def get_name
    return @name
  end
end

# I have just created an CAT using the Animal blueprint
cat = Animal.new("Hello Kitty")

# A dog is a subset of animal. So, a dog should inherit the properties / functions / characteristics of an aniaml
class Dog < Animal
    # I have not defined anything inside here yet
    def bark
      puts "The dog is barking"
    end
end

dog = Dog.new("Bobby")

puts dog.get_name
dog.bark

class Circle
   
    # shared within a class -> @@
    @@PI = 3.141592

    def initialize
        @radius = 0
    end

    def set_radius(radius)
        # shared within an instance => @
        @radius = radius
    end

    def area
      @radius * @radius * @@PI
    end

    def get_radius
      @radius
    end

end

c = Circle.new # this is a new instance of the class Circle

puts c.get_radius
puts c.area

c.set_radius(5)
puts c.get_radius
puts c.area

# super
# The super method calls the constructor of the parent class.

class Being 
end

class Living < Being 
end

class Mammal < Living 
end

class Human < Mammal 
end
    
    
p Human.ancestors
```

// Dale

```ruby
class Book
  def initialize(name)
    puts "New book created"
    @name = name
  end
  def set_name(name)
    @name = name
  end
  def get_name
    @name
  end
  def set_length(length)
    @length = length
  end
  def get_length
    @length
  end
  def set_author(author)
    @author = author
  end
  def get_author
    @author
  end
end

class TextBook < Book
  def set_topic(topic)
    @topic = topic
  end
  def get_topic
    @topic
  end
  def set_exercises(exercises)
    @exercises = exercises
  end
end

book = TextBook.new("Programming for Junkies")
book.set_length("5 pages")
book.set_topic("Computer Science")
```

// Vivien
```ruby
class Material

  def initialize(name)
    puts "The total cost of the material."

    @name = name
  end

  def net_cost
    return @cost
  end

  def delivery_cost
    return @delivery_cost
  end

  def destroy_cost
    return @destroy_cost
  end

  def total_cost
    return @net_cost + @delivery_cost + @destroy_cost
  end

end 


# class Equation

#   def initializ
#     @depth = 100
#     @length = 200
#   end

#   def set_cost(cost)
#     @cost = cost
#   end

#   def area
#     @depth * @length * 1.2
#   end

#   def get_cost
#     @cost
#   end

#   def amount
#     @depth * @length * 1.2 * @total_cost
#   end
# end

material = Material.new(Aluminium)

class Aluminium < Material

  def overprice
    puts "The cost is overprice."
  end
end

# e = Equation.new

puts e.get_cost
puts e.area

c.set_depth 105
c.set_length 205
puts e.area
puts e.amount
```

// Dow
```ruby
class CostOfCapital
  
  @@risk_free_rate = 0.02
  @@beta = 1
  @@equity_premium = 0.03

  def calculate
    @@risk_free_rate + @@beta * @@equity_premium
  end

end


class ValuePerpetual < CostOfCapital

  def interest_payment
    @payment = 1000
  end

  # def second_equation
  #   @payment / (@@risk_free_rate + @@beta * @@equity_premium)
  # end

end

c = ValuePerpetual.new

puts c.interest_payment / c.calculate
```
// Cassie
```ruby
class Parent

  def initialize()
    puts "congrats! you're a parent now!"

  end

  def play
    puts "time to play with the baby"
  end

  def read
    puts "reading bed-time story to baby"
  end

end

class Mommy < Parent
  def breastfeeding
    puts "mommy is breastfeeding"
  end

  def kiss 
    puts "mommy kisses baby"
  end
end
```

// Clement
```ruby
class Insect
  def initialize(name)
    puts "An insect called #{name} has been created"
    @name = name
    # return @name
  end
end

class Mosquito < Insect
  def be_annoying
    puts "buzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzzz"
  end
  
  def eat
    puts "drinking your blood"
  end
end

mozzy = Mosquito.new("Bob")
mozzy.be_annoying
mozzy.eat
```
// Denis
```ruby
class User
  def get_email
    return @email
  end

  def change_email(email)
    @email = email
    puts "email changed"
  end

  def get_password
    return @password
  end

  def change_password(password)
    @password = password
    puts "password changed"
  end
end

class Member < User
  def initialize(email, password)
    @email = email
    @password = password
    @public_privilage = true
    @admin_privilage = false
    puts "new member with email: " + @email + ", password: " + @password
  end
end

member = Member.new("test@test.com", "123456")

puts member.get_password

member.change_password("654321")

puts member.get_password
```

