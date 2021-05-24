# Fluent C++ Dailies
Notes and hands on coding of [Fluent C++ Dailies Posts](https://www.fluentcpp.com/posts/)

1. [`class` vs `struct`](https://www.fluentcpp.com/2017/06/13/the-real-difference-between-struct-class/)
 - The _legal_ difference is that the `class` members are `private` by default, `struct` members are `public` by default.

- `struct` is more commonly used to "bundle" together related elements in a certain context. It can also be used effectively to raise the level of abstraction to make function interfaces cleaner.

- `class` is about "doing things" - users of a class isn't supposed to know the context of the class, they care about the responsibility of the class ("what it does"), via the interface. 

- A class contains **invariants** - a relation between a class' data members in order for the class methods to work correctly. Ex: For a `std::string` that holds a `char*` and an `int size`, the invariant is the number of characters in the allocated `cahr` buffer must match the value of `size` memeber. 

**Invariants** are set in place by the class constructor, and the class methods assue that all invariants are true when the methods are called, and ensure that they remain true until the end.

- Rule of thumb: 
 - use `class` if there is at least one non-`public` member 
 - use `class` if there is an invariant, `struct` if the members can vary indepently

