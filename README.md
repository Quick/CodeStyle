# Code Style
Coding Styles for the Quick & Nimble Projects. Feedback is welcomed as issues and pull requests.

**Currently this is under discussion and does not apply to Quick and Nimble.** This isn't anywhere near final at the moment.

# Table of Contents
<!-- START doctoc -->
<!-- END doctoc -->

# Questions

- Objective-C Code Style? This is currently only swift

# Spacing

- 4 spaces indentation. No tabs.
- Don't leave trailing whitespace, even for blank lines.
- End files with a new line

Methods with braces always open same line. `else` does not close on a new line:

```swift
if expression {
    // do something
} else {
    // do something else
}
```

This includes `if`, `else`, `switch`, `struct`, `class`, `while`, `for`, `do`, closures/blocks. If they span multiple lines, they should still be at the end of the last line:

```swift
if expression && other_expression && whoa_I_need_to_wrap {
    // do something
}
```

`:` should have one space to the right:

```swift
class Foo: Bar {
}

struct Baz: Laz {
}

var count: Int

func foo<T: Equatable>(value: T) -> 
```

- There should be one space between methods and functions.
- No spaces between parenthesises: `(1 + 2)`
- Spaces should surround:
	- operators: `1 + 1` or `a += 2`
	- assignment, including default parameters: `func f(value: Int = 0)`
	- arrows: `func foo() -> Bar`

# Documentation

All public functions, methods, and types must be documented. As a rule of thumb, documentation comments should:

- Describe the purpose they're trying to solve or provide a convienence for.
- Hard-wrapped at 80 characters.
- Describe how the input parameters change the behavior.
- Caveats of implementation details that leak through from the implementation.

This doesn't exclude implementation comments that mention a bug or workaround or useful pointers to other parts of related code (such as mentioning files where a type's extensions will be).

# Declarations

Prefer declaring immutable variants over mutables ones when possible.

- Use `internal` explicitly instead of implicitly. If `internal` is used to describe a struct or class, then it's methods and variables can be implicit.
- Prefer `let` over `var`.
- Prefer `struct` over `class` when you do not have to using `mutating`

# Optionals

Use `if let` to check for optionals if the wrapped value is intended to be used, otherwise use `if value != nil`.

Avoid using `!` optional unwrapping operations. Only use it to describe internal variables that are known to be initialized prior to use.

# Blocks / Closures

Using trailing closure syntax whenever applicable. Keep the input arguments on the same line:

```swift
map(numbers) { number in
}
```

Avoid passing many arguments into closures.

Avoid `$N` argument notation unless it can fit in one small operation and be on the same line:

```swift
map([1, 2, 3]) { $0 + 1 }
```

# Literals

TBD

# Categories / Extensions

TBD