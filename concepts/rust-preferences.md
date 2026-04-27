# Rust Preferences

My preferences for Rust code.
These address the patterns agents most commonly get wrong.

## Zero-cost idioms

Strongly prefer the type that avoids unnecessary cost. Let the compiler do the work.

- **Stack over heap** when the size is known. `[u32; 3]` over `Vec<u32>` for fixed-size data. `Box` only when you need indirection or dynamic sizing.
- **Borrow over own** when you don't need ownership. `&str` over `String`, `&[T]` over `Vec<T>` in function signatures. Take ownership only when the function needs to store or move the value.
- **Iterators over intermediate collections.** Chain iterator operations instead of collecting into a `Vec` to process further. Collect at the end, not in the middle.
- **`Copy` types by value.** Don't borrow small `Copy` types like integers, bools, or small structs. Pass them by value.
- **`Cow` when ownership is conditional.** When a function sometimes borrows and sometimes owns, use `Cow<'_, str>` or `Cow<'_, [T]>` instead of always cloning.
- **Avoid `clone()` as a reflex.** Every `.clone()` should have a reason. If it's there to satisfy the borrow checker, that's often a sign the ownership model needs rethinking.

## Modern patterns

- **Error propagation**: `?` over `.unwrap()` in any code path that can fail. Reserve `.unwrap()` for cases where the invariant is obvious or documented.
- **Return types**: `impl Trait` over `Box<dyn Trait>` when the concrete type doesn't need to be named and there's a single return type.
- **Early returns**: `let-else` for early returns on pattern match failure instead of `match` with a single arm and a wildcard.
- **Module layout**: `foo.rs` + `foo/` over `foo/mod.rs`.

## Imports

- Everything imported at the top of the module scope.
  Don't use qualified paths in function bodies (`std::fs::read(path)`) — import the module at the top and use `fs::read(path)`.
  The reader should see all dependencies at a glance.
- Merge `use` statements as aggressively as possible.
  Combine imports from the same crate into a single `use` statement with nested braces.

  // Trait import: `io::Read` must be in scope for `.read_to_string()`.
  use io::Read;
  ```
  When a trait must be in scope for method calls, import it separately with a short comment explaining why.

## Comments and formatting

- Semantic line breaks in comments.
  Break at sentence boundaries or natural semantic units, not at arbitrary column widths.
  Each line should be a complete thought.
- Consistent punctuation.
  Periods at the end of sentences in doc comments and inline comments.
  Short list items can skip them, but be consistent within a block and across the file.
- Line breaks between enum variants and struct fields that have doc comments.
- `#[allow(...)]` and `#![allow(...)]` should have a comment explaining why.
  If the allow is temporary, use a TODO with an issue number or removal condition.
  If it's permanent, a short rationale is enough.
  The goal is readability — a future reader should understand why the allow is there without digging through git blame.
- `use super::*;` in test modules goes immediately after `mod tests {` with a blank line before other imports.

## Libraries

- **Time**: Prefer `jiff` over `chrono`.
