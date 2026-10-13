ref: depende da mutabilidade da variável
iref: não depende da mutabilidade da variável

## não altera valor nem endereço - Explorar versatilidade
```rust
let a: u8 = 1; // 0xa
let b: u8 = 2; // 0xb
ref r: u8 = a; // 0xa
```
```rust
let/var a: u8 = 1; // 0xa
let/var b: u8 = 2; // 0xb
let p: &u8 = &a; // 0xa
*p = 7; // erro
p = &b; // erro
p = &mut b; // erro
```
```rust
let a: u8 = 1; // 0xa
let/var b: u8 = 2; // 0xb
let p: &mut u8 = &mut a; // ERRO DE COMPILAÇÃO
*p = 7; // erro
p = &b; // erro
p = &mut b; // erro
```

## altera valor, mas não endereço - Explorar versatilidade
```rust
let a: u8 = 1; // 0xa
let/var b: u8 = 2; // 0xb
ref r: u8 = a; // 0xa
r = 7;
```
```rust
var a: u8 = 1; // 0xa
let/var b: u8 = 2; // 0xb
let/var p: &mut u8 = &mut a; // 0xa
*p = 7; // ok
p = &b; // erro
p = &mut b; // erro
```
## não altera valor, mas altera endereço - Explorar versatilidade
```rust
VOU PENSAR
```
```rust
let/var a: u8 = 1; // 0xa
let b: u8 = 2; // 0xb
var p: &u8 = &a; // 0xa
*p = 7; // erro
p = &b; // ok
p = &mut b; // erro
```
```rust
let/var a: u8 = 1; // 0xa
var b: u8 = 2; // 0xb
var p: &u8 = &a; // 0xa
*p = 7; // erro
p = &b; // ok
p = &mut b; // ok
```
## altera valor e endereço - Explorar versatilidade
```rust
var a: u8 = 1; // 0xa
var b: u8 = 2; // 0xb
var p: &mut u8 = &mut a; // 0xa
*p = 7; // ok
p = &b; // erro
p = &mut b; // ok
```
