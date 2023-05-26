Note: This repository has been archived.
To find my work on this project see the [official repository](https://github.com/fprasx/effect-cell)
or my [fork](https://github.com/ScratchCat458/effect-cell) for work-in-progress patches. 

# Effect Cell

A slimed down implementation of the Observer pattern using Rust's `Fn` trait.
Extended from [Felix Prasanna's](https://github.com/fprasx) project of the same name.

- [Original Project](https://github.com/fprasx/effect-cell)
- [Blog Post](https://users.rust-lang.org/t/comments-feedback-on-crate-idea/94096)

## Operator Passthrough
The `XAssign` traits have been setup so that they can modify the internal data
without the need for a call through `update_lambda`.
They will always call effects.

```rust
use effect_cell::EffectCell;

fn main() {
    let mut effect_cell = EffectCell::new(0);
    effect_cell.bind(|data| {println!("{data}");});
    effect_cell += 1;
    // Prints "1"
}
```

## Documentation
Since this is a derivative project, rustdoc is hosted locally using Github Actions.

Documentation - [https://scratchcat458.github.io/effect_cell](https://scratchcat458.github.io/effect_cell) 
