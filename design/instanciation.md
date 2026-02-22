## Reason
A `class` or `struct` don't need an automatic class constructor and explicit fields, is confusing and unnecessary

## Proposal
use the automatic class constructor like syntax to declare an aggregate and constructor syntax to instanciate:
```rust
class Cl(a: u8, b: u8, c: u8) {
  d: u8 = 4 # a field here must be initialized, otherwise a message error is showed
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

  # you can't mixing named and positional arguments, unless you mix the trailing named arguments
  let cl14: Cl = Cl{a: 1, 3, b: 2} # error:
# Argument already passed for this parameter.
# No value passed for parameter 'c'.

  let cl15: Cl = Cl{a: 1, c: 3, 2} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'b'.

  let cl16: Cl = Cl{b: 2, 1, 3} # error: 
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.
# No value passed for parameter 'c'.

  let cl17: Cl = Cl{b: 2, a: 1, 3} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'c'.

  let cl18: Cl = Cl{b: 2, 3, a: 1} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'c'.

  let cl19: Cl = Cl{b: 2, c: 3, 1} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.

  let cl20: Cl = Cl{c: 3, 1, 2} # error:
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
# No value passed for parameter 'a'.
# No value passed for parameter 'b'.

  let cl21: Cl = Cl{c: 3, a: 1, 2} # error:

}
```
