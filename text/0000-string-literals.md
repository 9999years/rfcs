- Feature Name: `string-literals`
- Start Date: 2021-12-02
- RFC PR: [rust-lang/rfcs#0000](https://github.com/rust-lang/rfcs/pull/0000)
- Rust Issue: [rust-lang/rust#0000](https://github.com/rust-lang/rust/issues/0000)

# Summary
[summary]: #summary

Assign the syntax `s"<string-contents>"` to mean `String::from("<string-contents>")`.

# Motivation
[motivation]: #motivation

`"<string-contents>".to_owned()` is 10 characters longer than it needs to be.
Most other languages to not make constructing string literals so hard. It's cumbersome in unit tests.

This RFC proposes making `s"<string-contents>"` syntax sugar for `String::from("<string-contents>)`.

# Guide-level explanation
[guide-level-explanation]: #guide-level-explanation

Constructing an owned `String` from a `&'static str` literal is such a common
case that the syntax `s"<string>"` is reserved for it.

```
let foo: String = s"foo";
```

# Reference-level explanation
[reference-level-explanation]: #reference-level-explanation

> **Lexer**
>
> OWNED_STRING_LITERAL : `s` STRING_LITERAL

An *owned string literal* is a string literal of type `std::string::String`,
written by prefixing an `s` to a string literal.

Examples:

```rust
s"foo";    // String::from("foo")
```

# Drawbacks
[drawbacks]: #drawbacks

# Rationale and alternatives
[rationale-and-alternatives]: #rationale-and-alternatives

# Prior art
[prior-art]: #prior-art

# Unresolved questions
[unresolved-questions]: #unresolved-questions

# Future possibilities
[future-possibilities]: #future-possibilities
