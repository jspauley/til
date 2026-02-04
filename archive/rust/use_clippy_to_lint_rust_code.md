# Use Clippy to Lint Rust Code

If you want to catch common mistakes and write more idiomatic Rust, Clippy is your go-to tool. It's Rust's official linter and comes bundled with rustup.

Run it on any Cargo project:

```bash
cargo clippy
```

For CI pipelines, treat warnings as errors:

```bash
cargo clippy -- -D warnings
```

Clippy catches things like using `.unwrap()` when `if let` is cleaner, unnecessary allocations, or redundant clones. For example, it'll flag this:

```rust
if option.is_some() {
    let val = option.unwrap();
}
```

And suggest:

```rust
if let Some(val) = option {
    // use val
}
```

You can enable stricter lints by adding this to your `lib.rs` or `main.rs`:

```rust
#![warn(clippy::pedantic)]
```

When you need to silence a lint, document why:

```rust
#[allow(clippy::cast_possible_truncation)] // Value guaranteed < 256
let byte = large_value as u8;
```

Run `cargo clippy --fix` to auto-apply simple suggestions. That's it!
