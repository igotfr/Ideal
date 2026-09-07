```rust
struct St(
  a: u8,
  b: u8,
  c: u8
) {
  field_non_instantiable_initialized: u8 = 4

  ctor cn(a, b = 6) [c = 8] {}

  // equivalent to
  //fn cn(a: u8, b: u8 = 6): Self => ret Self{a, b, 8}
  fn cn(a: u8, b: u8 = 6): Self => ret Self{field1: a, field2: b, field3: 8}

  mtd (shrd self) sum_fields(): u8 => self.a + self.b + self.c + self.field_non_instantiable_initialized

  fn check(value: u8): String =>
    ret if value > 120 -> "Invalid value"
    else -> "ok"
}

fn main() {
  let init_with_constructor: St = St::cn(8)

  println!(init_with_constructor.field_non_instantiable_initialized) // 4
  println!(init_with_constructor.sum_fields()) // 10

  println!(St::check(45))

  let st1: St = St{a: 1, b: 2, c: 3}

  // or change the order
  let st2: St = St{a: 1, c: 3, b: 2}

  let st3: St = St{b: 2, a: 1, c: 3}

  let st4: St = St{b: 2, c: 3, a: 1}

  let st5: St = St{c: 3, a: 1, b: 2}

  let st6: St = St{c: 3, b: 2, a: 1}

  // alternatlivelly, the field names can be ommited
  let st7: St = St{1, 2, 3}

  // or ommit only a few of them
  let st8: St = St{a: 1, b: 2, 3}

  let st9: St = St{a: 1, 2, c: 3}

  let st10: St = St{a: 1, 2, 3}

  let st11: St = St{1, b: 2, c: 3}

  let st12: St = St{1, b: 2, 3}

  let st13: St = St{1, 2, c: 3}

  // you can't mixing named and positional arguments, unless you shuffle only the trailing named arguments that are yet not passed
  let st14: St = St{1, c: 3, b: 2} // ok

  let st15: St = St{a: 1, 3, b: 2} // error:
// Argument already passed for this parameter.
// No value passed for parameter 'c'.

  let st16: St = St{a: 1, c: 3, 2} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'b'.

  let st17: St = St{b: 2, 1, 3} // error: 
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'a'.
// No value passed for parameter 'c'.

  let st18: St = St{b: 2, a: 1, 3} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'c'.

  let st19: St = St{b: 2, 3, a: 1} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'c'.

  let st20: St = St{b: 2, c: 3, 1} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'a'.

  let st21: St = St{c: 3, 1, 2} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'a'.
// No value passed for parameter 'b'.

  let st22: St = St{c: 3, a: 1, 2} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'b'.

  let st23: St = St{c: 3, 2, a: 1} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'b'.

  let st24: St = St{c: 3, b: 2, 1} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'a'.

  let st25: St = St{c: 3, 1, b: 2} // error:
// Mixing named and positional arguments is not allowed unless the order of the arguments matches the order of the parameters.
// No value passed for parameter 'a'.
}
```