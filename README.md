# Ruby 101

Ruby is what we called a programming language.

It has the particularity to be focused on simplicity and productivity by using an elegant syntax that is natural to read and easy to write.

## Objectives

- Describe variables and data types

- Identify conditions and loops

- Define & write a function




## How to run Ruby code

1. In IRB

   You can run `irb` in the terminal to launch a Ruby interpreter. You can see it as a playground to test things out.

2. Using Ruby files

   Using Ruby files, for example `wagon.rb`. Launch your Ruby script from the terminal with:

   ```bash
   ruby path/to/your/file.rb
   ````


3. Using online Ruby interpreter

    You can go on https://repl.it/ to get a Ruby interpreter without having to download anything.

# Ruby types

### Strings

- To represent text
- Defined with single quotes or double quotes: `'wagon'` or `"wagon"`

```ruby

puts "wagon"              # => wagon
puts "Hey" + " Le Wagon"  # => Hey Le Wagon

puts "wagon".upcase       # => WAGON
puts "wagon".capitalize   # => Wagon
```

### Integers

- To represent integers
- Can do standard arithmetic

```ruby
puts 1 + 2                # => 3
puts 2 * 4                # => 8
```

- Also has custom methods built-in

```ruby
puts 20.even?             # => true
puts 20.odd?              # => false
```

### Booleans

- To represent something that is true or false

```ruby
puts 1 > 2 # => false
puts 2 > 1 # => true
```

### Arrays

- To represent list of elements, usually of the same type
- Defined with square brackets around the list of items
- Has it's own built-in methods

```ruby
puts ["paris", "london", "new york"].length    # => 3
p ["paris", "london", "new york"].sort      # => ["london", "new york", "paris"]
p [3, 5, 1].sort                            # => [1, 3, 5]
```

- You access elements in an array based on its **index**, careful, indexes start at 0

```ruby
beatles = ["john", "paul", "george", "ringo"]

puts beatles[0]         # => john
puts beatles[2]         # => george
```

- You add an element to an array by **appending** it or **inserting** it at a given **index**

```ruby
beatles = ["john", "george"]

beatles << "ringo"
beatles.insert(1, "paul")
p beatles          # => ["john", "paul", "george", "ringo"]
```

- You modify an element in an array using its **index** again

```ruby
beatles = ["john", "alex", "george", "ringo"]

beatles[1] = "paul"
p beatles          # => ["john", "paul", "george", "ringo"]
```

- You delete an element from an array by using its **index** or by using its value

```ruby
beatles = ["john", "paul", "alex", "george", "arthur", "ringo"]

beatles.delete_at(2)
beatles.delete("arthur")
p beatles          # => ["john", "paul", "george", "ringo"]
```


## Variables

- Allows you to store values to reuse them later
- You **assign** a value to a variables
- Variables can be overwritten and incremented

```ruby
age = 21
puts age # => 21

```


### Built-in methods

The built in methods are well-documented, don't reinvent the wheel...

- [String methods](https://ruby-doc.org/core-2.3.3/String.html)
- [Fixnum methods](https://ruby-doc.org/core-2.3.3/Fixnum.html)
- [Floats methods](https://ruby-doc.org/core-2.3.3/Float.html)
- [Array methods](https://ruby-doc.org/core-2.3.3/Array.html)
- [Hash methods](https://ruby-doc.org/core-2.3.3/Hash.html)
- [Enumerable methods](https://ruby-doc.org/core-2.3.3/Enumerable.html)

## Flow Control

Conditionals and loops change the flow of a Ruby program. Conditionals allow us to execute a certain chunk of code under a specific condition. Loops allow us to execute a chunk of code multiple times. When the program is run, the code is executed from top to bottom, line by line, which is how you should debug in your head.

### Conditionals (If/Unless)

#### If

If conditionals allow us to execute a certain chunk of code if a condition is "thruthy".

```ruby
if condition
  # code executed only when condition is "truthy"
end
```

#### If/Else

If/Else conditionals allow us to execute a certain chunk of code if a condition is "thruthy" **or** another chunk of code if the same condition is **not** "truthy".

```ruby
if condition
  # code executed only when condition is "truthy"
else
  # code executed only when condition is not "truthy"
end
```

For example, a small Ruby program that checks if you are old enough to vote:

```ruby
age = 20

if age >= 18
  puts "You can vote!"
else
  puts "You cannot vote!"
end
```

#### Combining conditions

- You can combine condition with `&&` which is the logical AND, or `||` which is the logical OR.
- You can negate a condition with a `!` in front of the condition

### Loops (While/Until/For)

#### While

While loops allow us to execute a chunk of code multiple times while a condition is "truthy".

```ruby
while condition
  # executed while condition is truthy
end
```

For example, a small Ruby program that replicates the 'Price is Right' game.

```ruby
counter = 1

while counter < 6
  puts counter
  counter = counter + 1
end

```

#### For

For loops allow us to execute a chunk of code for a given amount of times, based on the inputs of the for loop.

```ruby
for num in [1, 2, 3, 4, 5]
  puts "Hey"
end
```

In the example above, the for loop will loop 5 times, with num being equal to the corresponding element in the array on each loop.

## Methods

- Concise way to call Ruby code multiple times
- Apply the ruby code to dynamic inputs
- Defined with **parameters** and called with **arguments**
- A method always returns a result, and you can then operate on what is returned

```ruby
def say_hi(first_name)
  sentence = "Hey " + first_name.capitalize + "!"
  return sentence
end

puts say_hi("charly") # => Hey Charly!
```

- In the example above, `first_name` and `last_name` were parameters and `"boris"` and `"paillard"` were the arguments, and we `puts` what returned from the method call
- We can call the method with variables too

# Challenges

### Challenge 1

Print out the numbers 1 to 8 using a for loop.

You should see something like that:

```bash
   1
   2
   3
   4
   5
   6
   7
   8
````

Solution:

```ruby

\first solution

for num in [1,2,3,4,5,6,7,8]
  puts num
end


for num in (1..8).to_a
  puts num
end

```

### Challenge 2

Print out 5 times "hello" using a while loop.

You should see something like that:

```bash
  hello
  hello
  hello
  hello
  hello
````

Solution:

```ruby

counter = 1

while counter < 6
  puts "hello"
  counter = counter + 1
end


while counter < 6
  puts "hello"
  counter += 1
end

```

### Challenge 3

Copy paste this:

```ruby
first_name = "john"
last_name = "lennon"
full_name = ???

puts full_name

```

Change the value of full_name to get something like this:

```bash
John LENNON
````

Solution:

```ruby

first_name = "john"
last_name = "lennon"
full_name = first_name.capitalize + " " + last_name.upcase

full_name2 = "#{first_name.capitalize} #{last_name.upcase}"

puts full_name
puts full_name2
```

### Challenge 4

Copy paste this:

```ruby

array_of_cities = ["Paris", "London", "Melbourne", "Tokyo"]

```

- Print out the third value of this array.

- Add Sydney to this array and print out the new array.

- Delete Melbourne from it and print out the new array.

- You should see something like that:

```bash
Melbourne
["Paris", "London", "Tokyo"]
["Paris", "London", "Tokyo", "Sydney"]
````

Solution:

```ruby

array_of_cities = ["Paris", "London", "Melbourne", "Tokyo"]

puts array_of_cities[2]
array_of_cities.delete("Melbourne")
p array_of_cities
array_of_cities.insert(2, "Sydney")
p array_of_cities

array_of_cities2 = ["Paris", "London", "Melbourne", "Tokyo"]

puts array_of_cities2[2]
array_of_cities2[2] = "Sydney"
p array_of_cities2
```

### Challenge 5

Copy paste this:

```ruby

current_hour = Time.now.hour

```

It will store the current hour in a variable named current_hour. Now create an if statement to print out "I am hungry!" if current_hour is bigger than 12.

Change the value of current_hour to see if it works.

Solution:

```ruby
current_hour = Time.now.hour

if current_hour > 12
  puts "I am hungry!"
end


puts "I am hungry!" if current_hour > 12


```

### Challenge 6

Copy paste this:

```ruby
students = ["Julie", "Ben", "Beatrice"]
```

Combine a for loop and an if statement inside of the loop to print out every name that starts with a "B".

Solution:

```ruby
current_hour = Time.now.hour

if current_hour > 12
  puts "I am hungry!"
end


puts "I am hungry!" if current_hour > 12


```


### Challenge 7

Copy paste this:

```ruby
<!-- your code here -->

puts only_name_with_first_letter(["Charly", "Cedric", "Hugo"], "C")
```

Create a function called only_name_with_first_letter that prints out all students names that start with a specific letter. The function takes two parameters:
1) An array of students 2) A letter
Copy paste this:

You should see something like this:

```bash
Charly
Cedric
````



