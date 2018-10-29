---
layout: post
title: "Ruby: class methods vs. instance methods"
---

In Ruby, a _method_ provides functionality to an Object. A _class method_ provides functionality to a class itself, while an _instance method_ provides functionality to one instance of a class.

Consider the following Ruby class:

```ruby
class SayHello
  def self.from_the_class
    "Hello, from a class method"
  end

  def from_an_instance
    "Hello, from an instance method"
  end
end
```

This would yield the following:

```
>> SayHello.from_the_class
=> "Hello, from a class method"

>> SayHello.from_an_instance
=> undefined method `from_an_instance' for SayHello:Class


>> hello = SayHello.new
>> hello.from_the_class
=> undefined method `from_the_class' for #<SayHello:0x0000557920dac930>

>> hello.from_an_instance
=> "Hello, from an instance method"
```

We cannot call an instance method on the class itself, and we cannot directly call a class method on an instance.

[Railstips](http://www.railstips.org/blog/archives/2009/05/11/class-and-instance-methods-in-ruby/) has a nice article with more detail and a discussion of alternative ways of creating both class methods and instance methods.

---

(_This post first appeared on [dev.to](https://dev.to/adamlombard/ruby-class-methods-vs-instance-methods-4aje)_.)