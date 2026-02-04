# Using Clippy to Lint Rust Code

Clippy is Rust's official linting tool that catches common mistakes and enforces idiomatic patterns. Run it regularly to improve code quality.

## Basic Usage

```bash
# Run clippy on your project
cargo clippy

# Include tests, examples, and benchmarks
cargo clippy --all-targets

# Fail on warnings (for CI)
cargo clippy -- -D warnings

# Auto-fix where possible
cargo clippy --fix
```

## Configure Lints in Cargo.toml

```toml
[lints.clippy]
pedantic = { level = "warn", priority = -1 }
unwrap_used = "warn"
expect_used = "warn"
correctness = "deny"
```

## Suppress Specific Lints

```rust
#[allow(clippy::too_many_arguments)]
fn complex_fn(a: i32, b: i32, c: i32, d: i32, e: i32, f: i32, g: i32) {}
```

## Common Fixes Clippy Suggests

```rust
// Bad: v.len() == 0
// Good:
v.is_empty()

// Bad: match opt { Some(x) => Some(x * 2), None => None }
// Good:
opt.map(|x| x * 2)

// Bad: if let Some(_) = opt { }
// Good:
if opt.is_some() { }
```

Key lint categories: `correctness` (bugs), `perf` (inefficiencies), `style` (idioms), `pedantic` (stricter, off by default). Always use `--all-targets` in CI to catch issues in test code.