## Functions
```rust
fn f(a: u8, b: f32): f32 {
  return a as f32 + b
}

f(4, 3.2);
```
## Methods
> **<sup>Syntax</sup>**\
> _Method_ :\
> &nbsp;&nbsp; _MethodQualifiers_ `mtd` [_GenericParams_]<sup>?</sup>&nbsp;`(` _MethodParameters_<sup>?</sup> `)` [IDENTIFIER]&nbsp; `(` _MethodParameters_<sup>?</sup> `)`\
> &nbsp;&nbsp; &nbsp;&nbsp; _FunctionReturnType_<sup>?</sup> [_WhereClause_]<sup>?</sup>\
> &nbsp;&nbsp; &nbsp;&nbsp; ( [_BlockExpression_] | `;` )
>
> _FunctionParameters_ :\
> &nbsp;&nbsp; &nbsp;&nbsp; _SelfParam_ `,`<sup>?</sup>\
> &nbsp;&nbsp; | (_SelfParam_ `,`)<sup>?</sup> _FunctionParam_ (`,` _FunctionParam_)<sup>\*</sup> `,`<sup>?</sup>
>
```rust
mtd (a: u8) m(b: 32): f32 {
  return a as f32 + b
}

4.m(3.2);
```
## Lambdas
```rust
lbd l(a: u8, b: f32): f32 {
  return a as f32 + b
}

// or immutable
lbd l(a: u8, b: f32): f32 = f;

l = g; // error

// or mutable
vlbd l(a: u8, b: f32): f32 = f;

l = g; // ok

l(4, 3.2);
```
## Method Lambdas
```rust
mlbd (a: u8) l(b: f32): f32 {
  return a as f32 + b
}

// or immutable
mlbd (a: u8) l(b: f32): f32 = f;

l = g; // error

// or mutable
vmlbd (a: u8) l(b: f32): f32 = f;

l = g; // ok

4.l(3.2);
```
