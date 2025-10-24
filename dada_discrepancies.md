## Keywords
| Ideal | Dada |
| :---: | :--: |
| `var` | `mut` |
| `ret` | `return` |

## Permissions
| Ideal | Dada |
| :---: | :--: |
| `own` / `ownd` | `give` / `given`, `owned`, `my` |
| `shr` / `shrd` | `share` / `shared`, `our` |
|||
| `ptr` / `ptrd` | `ref` / |
| `mptr` / `mptrd` | / `lent` |
|||
| `uptr` or `rptr` / `uptrd` or `rptrd` ||
| `umptr` or `rmptr` / `umptrd` or `rmptrd` ||
|||
| `ref` / `refd` ||
| `mref` / `mrefd` ||
|||
| `uref` or `rref` / `urefd` or `rrefd` ||
| `umref` or `rmref` / `umrefd` or `rmrefd` ||

`m` in `mptr` means mutable

`u` in `uptr` means unsafe

`r` in `rptr` means raw

## Operators
| Ideal | Dada |
| :---: | :--: |
| `:` in return type | `->` in return type |

## Notations
| Ideal | Dada |
| :---: | :--: |
| StructInstance { /* fields */ } | StructInstance(/* fields */) |
| `each` elem `<-` iterator ||

## Missing
```rust
v: type T impl Trait
v: type T dyn Trait (idk)
```

alias of fields with variable with same name `:field`
