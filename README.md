# Flow Control

## Objectives
1. Define flow control for when a Ruby program is executed. 
2. Implement flow control in different ways.
3. Use `if`, `else`, and `elsif` statements to control flow.

## What is Flow Control?
> A control flow construct is a language feature which disrupts the normal progression to the next statement and conditionally or unconditionally branches to another location in source code.                                
> –– [Robert Klemme](http://blog.rubybestpractices.com/posts/rklemme/004-Control_Flow.html)

In other words, control flow let's you tell your program what code to execute conditionally. As humans, we actually enact flow control *every day*. For instance, if you are hungry, you will go and get a snack. Otherwise, you'll stay put and continue to read this awesome readme. 

Flow control is an important part of Ruby programming and web development. In the context of a web application, for example, you can easily think of content or functionality on a website you've visited that is only available to a user *if* that user is logged in.

## Implementing Flow Control

There are a number of ways to tell your program to conditionally execute certain code, the basic forms of which are:

* `if`, `else`, and `elsif` statements,
* `case` statements,
* loops.

In this reading, we're going to discuss the first group of these "conditional" statements: `if`, `else`, and `elsif`.

### `if` Statements

One of the most common ways to enact flow control is the `if` statement. Whatever block of code that follows the `if` statement will get evaluated—i.e. read and enacted by the computer. If this evaluation of the `if` statement results in `true`, then the code through to the associated `end` statement will run.

Let's look at a few examples:

```ruby
if true
  puts "Goats have rectangular pupils."
end
# └── "Goats have rectangular pupils."
```
* The code above will print `Goats have rectangular pupils.` because `true` evaluates as `true`.

Meanwhile:

```ruby
if false
  puts "A wolf can eat up to 20 pounds of meat in one sitting."
end
```
* The code above will not print anything because the `if` statement evaluates as `false`.

So what if we want our program to print something *else* when the `if` condition evaluates as `false`? 

### The `else` Keyword

To accomplish this, we can follow an `if` statement with an `else` statement. Take a look:

```ruby 
if false 
   puts "This will never get printed because the above
     statement evaluates to false."
else 
   puts "This will get printed!"
end
```

An `else` statement sets a "default" condition for when your `if` statement's conditional evaluates as `false`. Every condition that doesn't evaluate as `true` will instead pass through the `else` statement.

##### Further Examples

So far, we've seen `if` statements that rely on the explicit use of the `true` and `false` booleans. Let's look at some examples that require a little more thought. 

###### Example 1

```ruby
if 6 + 3 == 9
  puts "Giraffes have no vocal cords."
end
# └── "Giraffes have no vocal cords."
```
* The code above will print `Giraffes have no vocal cords` Since `6 + 3` equals `9` (i.e. `9` is equal to `9`), the `if` statement's conditional evaluates as `true`.

**Top-tip:** *Remember that the comparative operator* `==` *("double-equals") is used to check equality. This is distinct from the assignment operator* `=`*("single-equals"), which is used to set the value of a variable.*

###### Example 2

```ruby
if 6 + 3 < 5
  puts "The hummingbird is the only animal that can fly backwards"
end
```
* The code above will not print anything because `6 + 3`, which is equivalent to `9`, is *not* less than `5`, making the `if` statement's conditional evaluate as `false`.

###### Example 3

```ruby
dog = "satisfied"

if dog == "hungry"
  puts "Refilling food bowl."
else
  puts "Reading newspaper."
end

#  └── "Reading newspaper."
```
### `elsif` Statements

Sometimes, we want to control the flow of our program based on more than one condition. For example, if I am hungry, then I will get a snack. If I am thirsty, then I will get a drink of water. Otherwise, I will stay here and continue learning more about flow control.

We can add additional layers of complexity to our `if` and `else` statements by using the `elsif` keyword. 

Let's add an `elsif` statement to Example 3 from above:

```ruby
dog = "thirsty"

if dog == "hungry"
  puts "Refilling food bowl."
elsif dog == "thirsty"
  puts "Refilling water bowl."
else
  puts "Reading newspaper."
end

#  └── "Refilling water bowl."
```

We can cascade as many `elsif` statements as we wish, however `elsif` statements can only be used following an `if` statement, and must precede the associated `else` statement (if used).

```ruby
dog = "cuddly"

if dog == "hungry"
  puts "Refilling food bowl."
elsif dog == "thirsty"
  puts "Refilling water bowl."
elsif dog == "playful"
  puts "Playing tug-of-war."
elsif dog == "cuddly"
  puts "Snuggling."
else
  puts "Reading newspaper."
end

#  └── "Snuggling."
```

That's all for now—we'll discuss `case` statements and looping in upcoming lessons. 
