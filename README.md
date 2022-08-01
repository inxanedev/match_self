# match_self
Rust macro for the common "x = match x" pattern

# Usage
Have you ever written something like this?
```rust
really_long_variable_name = match really_long_variable_name {
    ...
}
```
The issue here is that we have to write the name `really_long_variable_name` twice.  
If we only had to do it once, there would really be no issue when it comes to the readability.  
However, there is no "match itself" syntax in Rust, and that is exactly what this crate provides!  
  
The crate defines a `match_self` macro, which takes a variable and lets you match itself, as the name suggests.
```rust
match_self!(really_long_variable_name, {
    ...
})
```
The macro is a declarative macro, and because of that, it has to imitate the syntax of regular Rust `match` statements. However, the macro expands into a normal match statement at compile time.