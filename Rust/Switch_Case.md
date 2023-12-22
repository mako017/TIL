# Switch Case

Switch statements in Rust can be used to match int, string or boolean variables with a given set of cases. There is no default fall through, therefore no breaks are needed. However, Switch statements must be exhaustive, so a default case `_` must be defined.

## Examples

### Matching int

```rust
fn main() {
    let num = 3;
    match num{
    1 => println!("One"),
    2 => println!("Two"),
    3 => println!("Three"),
    4|5|6 => println!("Four, Five, or Six"),
    _ => println!("Rest of the number"),
    }
}
```

### Matching string

If the default case is supposed to do nothing, put empty parentheses as instruction.

```rust
fn main() {
  let language = "German";
    match language{
        "German" => println!("This language is spoken in Germany"),
        "Japanese" => println!("This language is spoken in Japan"),
        _ => (),
    };
}
```

### Matching boolean

As demonstrated in this example, Switch statements can be used to return values.

```rust
fn main() {
  let win = false;
    let result = match win{
        false => "lost",
        true => "won",
    };
    println!("Player has {}.", result)
}
```

### [source](https://www.geeksforgeeks.org/rust-switch-case/)
