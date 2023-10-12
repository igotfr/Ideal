Type | Description
---- | :---------:
bool
u8, u16, u32, u64, u128, usize, ulong
i8, i16, i32, i64, i128, isize, ilong
comptime_int | Only allowed for comptime-known values. The type of integer literals
f16, f32, f64, f128
comptime_float | Only allowed for comptime-known values. The type of float literals
string
void or none | 0 bit type
noreturn | the type of break, continue, return, unreachable, and while (true) {}
null or none
type | the type of types
anyerror | an error code

## Primitives
Type | Description
---- | :---------:
Bool
U8, U16, U32, U64, U128, USize, ULong
I8, I16, I32, I64, I128, ISize, ILong
Comptime_Int | Only allowed for comptime-known values. The type of integer literals
F16, F32, F64, F128
Comptime_Float | Only allowed for comptime-known values. The type of float literals
String
Void or None | 0 bit type
Noreturn | the type of break, continue, return, unreachable, and while (true) {}
Null or None
Type | the type of types
Anyerror | an error code

## Values
undefined or Undefined

null or Null or None or none

0b1, 0o7, 0xf

___

12e3 == 12_000, 12E3 == 12_000 (depreacated because e is a hexadecimal)

12g3 == 12_000, 12G3 == 12_000

0xfp3 == 15 * 2 ^ 3, 0xfP3 == 15 * 2 ^ 3

0xf*2^3 == 15 * 2 ^ 3

___

'\b{1100001}' == 'a' == 97

'\o{172}' == 'z' == 122

'\x{65}' == 'e' == 101

'\u{1f4a9}' == 128169

___

'ABCD' : Multibyte Character literals
