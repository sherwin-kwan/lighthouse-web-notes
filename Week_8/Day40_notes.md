## Day 40 - 6 Nov 2020

* New instructor: Khurram Virani, Co-Founder of Lighthouse Labs
* Computer science grad from Guelph
* Did Java, and then Ruby - and then started a school
* Quirky fact: Loved drinking seawater as a kid in Pakistan

## Ruby Timeline

* Intro/Prep: until Mon
* Rails: Tue
* Jungle app: Project starts Wed
* Research & Reflection: Week 9 weekend

## Getting Started with Ruby

* HTTParty: library (gem) in Ruby
* no semicolons needed for end-of-line
* to import a gem: ```require name_of_gem```
* Note: Ruby does NOT have a project dependency system by default like *npm*. Ruby 3 will fix this, but until then, you need to install a gem called *bundler* to handle installing other gems
* This creates a file called *Gemfile* (equivalent to *package.json*) - however, unlike in Node, you get to do conditional statements (if this then install this)
* Variable names beginning with capital letters are constants in Ruby
* *Hash*: an object with key-value pairs in Ruby
* Putting parentheses () around arguments for a function is optional in Ruby. ```method arg1 arg2``` is valid Ruby.
* *Begin .... Rescue ....* is the try-catch block of Ruby
* To define a variable globally, use *@var = 12*, then you can refer to @var anywhere in the file

## Conventions

* Use snake_case for all variables
* Use "?" at the end of a method to specify that it returns a boolean. "allowed?" returns true if allowed, false if not
* Use "!" to designate a method as important

## Khurram's Tips

* Use .mdx files - you can turn these into slideshows
* Always use .inspect when logging values to console with *puts*
* Writing asynchronous code is easier in Ruby than in JS, but that's because Ruby is a blocking language