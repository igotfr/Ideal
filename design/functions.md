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
> &nbsp;&nbsp; _MethodQualifiers_ `mtd` [_GenericParams_]<sup>?</sup>&nbsp;`(` _MethodParameters_<sup>?</sup> `)` [IDENTIFIER]&nbsp; `(` _FunctionParameters_<sup>?</sup> `)`\
> &nbsp;&nbsp; &nbsp;&nbsp; _FunctionReturnType_<sup>?</sup> [_WhereClause_]<sup>?</sup>\
> &nbsp;&nbsp; &nbsp;&nbsp; ( [_BlockExpression_] | `;` )
>
> _MethodParameters_ :\
> &nbsp;&nbsp; &nbsp;&nbsp; _SelfParam_ `,`<sup>?</sup>\
> &nbsp;&nbsp; | (_SelfParam_ `,`)<sup>?</sup> _FunctionParam_ (`,` _FunctionParam_)<sup>\*</sup> `,`<sup>?</sup>
>
> _SelfParam_ :\
> &nbsp;&nbsp; [_OuterAttribute_]<sup>\*</sup> ( _ShorthandSelf_ | _TypedSelf_ )
>
> I don't know exactly how will it be _ShorthandSelf_ and _TypedSelf_
>
> _FunctionParam_ :\
> &nbsp;&nbsp; [_OuterAttribute_]<sup>\*</sup> (
>   _FunctionParamPattern_ | `...` | [_Type_] [^fn-param-2015]
> )
>
> _FunctionParamPattern_ :\
> &nbsp;&nbsp; [_PatternNoTopAlt_] `:` ( [_Type_] | `...` )
>
> _FunctionReturnType_ :\
> &nbsp;&nbsp; `->` [_Type_]
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
