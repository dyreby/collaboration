# Rust Preferences

Preferences for Rust code.

## Tooling

- **Linting**: `clippy::pedantic`, no warnings allowed.
- **Formatting**: Run `cargo fmt --check` before committing. CI usually enforces this.
- **Idiomatic Rust**: Modern, correct, take advantage of new features for readability.

## Imports

- Everything imported at the top of the module scope.
  No inline qualified paths (`std::fs::read`, `serde::Serialize`) unless it improves readability.
  The reader should see all dependencies at a glance.
- Merge as aggressively as possible.
  Combine imports from the same crate into a single `use` statement with nested braces.
  ```rust
  // Yes
  use std::{
      collections::HashMap,
      fs,
      io::{self, Read},
  };

  // No
  use std::collections::HashMap;
  use std::fs;
  use std::io::{self, Read};
  ```
- When importing a module (e.g., `use std::fs`), use the module path for its items in code (`fs::Metadata`, `fs::read`).
  Don't also import specific items from the same module — pick one level of abstraction.
- When a trait must be in scope for method calls (e.g., `io::Read` for `.read_to_string()`), import it separately below the grouped import with a comment explaining why.

## Test modules

- `use super::*;` goes immediately after `mod tests {` with a blank line after it, before any other imports.
  This establishes the module's own scope first, then adds external imports below.

## Comments

- Semantic line breaks. Break at sentence boundaries or natural semantic units, not at arbitrary column widths.
  Each line should be a complete thought.
  When near a natural wrap point, prefer the semantic break. Otherwise wrap at whatever makes sense or the linter suggests.
- Periods at the end of sentences unless inconsistent within formatting context (e.g., short list items without periods).
  Short sentence comments get the period.

## Formatting

- Line breaks between variants and fields that have doc comments.

## Allow directives

- `#[allow(...)]` and `#![allow(...)]` need a TODO comment saying why the allow exists and when it can be removed.
  Include an issue number when there is one.
  ```rust
  // TODO(#30): remove when voyage complete is wired to CLI
  // TODO: remove once we add Display impl
  ```

## Module style

- Modern — `foo.rs` + `foo/` over `foo/mod.rs`.

## Zero-cost idioms

Prefer the type that avoids unnecessary cost. Let the compiler do the work.

- **Stack over heap** when the size is known. `[u32; 3]` over `Vec<u32>` for fixed-size data. `Box` only when you need indirection or dynamic sizing.
- **Borrow over own** when you don't need ownership. `&str` over `String`, `&[T]` over `Vec<T>` in function signatures. Take ownership only when the function needs to store or move the value.
- **Iterators over intermediate collections.** Chain iterator operations instead of collecting into a `Vec` to process further. Collect at the end, not in the middle.
- **`Copy` types by value.** Don't borrow small `Copy` types like integers, bools, or small structs. Pass them by value.
- **`Cow` when ownership is conditional.** When a function sometimes borrows and sometimes owns, use `Cow<'_, str>` or `Cow<'_, [T]>` instead of always cloning.
- **Avoid `clone()` as a reflex.** Every `.clone()` should have a reason. If it's there to satisfy the borrow checker, that's often a sign the ownership model needs rethinking.

## Libraries

- **Time**: Prefer `jiff` over `chrono`.
