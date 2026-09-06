## [Language] Automatic class constructor and explicit fields simultaneously are confusing and unnecessary

https://github.com/dada-lang/dada/issues/262

## Reason
A `class` or `struct` don't need an automatic class constructor and explicit fields, it's confusing and unnecessary. I can't to have one when I have other, so to have both is unnecessary

## Proposal
use the automatic class constructor like syntax to declare or to implement an aggregate and constructor syntax to instantiate:
```rust
class Cl(a: u8, b: u8, c: u8) {
  d: u8 = 4 # a field here must be initialized, otherwise a error message is showed
}

async fn main() {
  let cl1: Cl = Cl{a: 1, b: 2, c: 3}

  # or change the order
  let cl2: Cl = Cl{a: 1, c: 3, b: 2}

  let cl3: Cl = Cl{b: 2, a: 1, c: 3}

  let cl4: Cl = Cl{b: 2, c: 3, a: 1}

  let cl5: Cl = Cl{c: 3, a: 1, b: 2}

  let cl6: Cl = Cl{c: 3, b: 2, a: 1}

  # alternatlivelly, the field names can be ommited
  let cl7: Cl = Cl{1, 2, 3}

  # or ommit only a few of them
  let cl8: Cl = Cl{a: 1, b: 2, 3}

  let cl9: Cl = Cl{a: 1, 2, c: 3}

  let cl10: Cl = Cl{a: 1, 2, 3}

  let cl11: Cl = Cl{1, b: 2, c: 3}

  let cl12: Cl = Cl{1, b: 2, 3}

  let cl13: Cl = Cl{1, 2, c: 3}

  # you can't mixing named and positional arguments, unless you shuffle only the trailing named arguments that are yet not passed
  let cl14: Cl = Cl{1, c: 3, b: 2} # ok

  let cl15: Cl = Cl{a: 1, 3, b: 2} # error:
# Argument already passed for this parameter.
# No value passed for parameter 'c'.

  let cl16: Cl = Cl{a: 1, c: 3, 2} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'b'.

  let cl17: Cl = Cl{b: 2, 1, 3} # error: 
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.
# No value passed for parameter 'c'.

  let cl18: Cl = Cl{b: 2, a: 1, 3} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'c'.

  let cl19: Cl = Cl{b: 2, 3, a: 1} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'c'.

  let cl20: Cl = Cl{b: 2, c: 3, 1} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.

  let cl21: Cl = Cl{c: 3, 1, 2} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.
# No value passed for parameter 'b'.

  let cl22: Cl = Cl{c: 3, a: 1, 2} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'b'.

  let cl23: Cl = Cl{c: 3, 2, a: 1} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'b'.

  let cl24: Cl = Cl{c: 3, b: 2, 1} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.

  let cl25: Cl = Cl{c: 3, 1, b: 2} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.
}
```

### Programming languages that allow named and positional arguments like in this proposal
Kotlin, Python, C#, PHP

C allows named and positional arguments strictly, not allowing to shuffle

## Alternative to avoid to expose parameter name to public API
```rust
# positional parameter or internal named parameter exposed to public API
fn|struct|class id(mut? p_to_public_api_and_inside_the_item: Type)

# call examples
id(4)
id(p_to_public_api_and_inside_the_item: 4)

# positional parameter or public named parameter exposed to public API and a internal parameter name
fn|struct|class id(mut? p_to_public_api p_inside_the_item: Type)

# call examples
id(4)
id(p_to_public_api: 4)

# forbid named parameter, allow only positional parameter
fn|struct|class id(mut? _ p_inside_the_item: Type)

# call examples
id(4)
id(p_inside_the_item: 4) # error

# to enforce to use internal named parameter exposed to public API
fn|struct|class id(mut? *p_to_public_api_and_inside_the_item: Type)

# or to enforce like in Python
fn|struct|class id(*, mut? p_to_public_api_and_inside_the_item: Type)

# call examples
id(4) # error
id(p_to_public_api_and_inside_the_item: 4)

# to enforce to use public named parameter exposed to public API and a internal parameter name
fn|struct|class id(mut? *p_to_public_api p_inside_the_item: Type)

# or to enforce like in Python
fn|struct|class id(*, mut? p_to_public_api p_inside_the_item: Type)

# call example
id(4) # error
id(p_to_public_api: 4)
```

## Correlated to
https://github.com/dada-lang/dada/issues/261