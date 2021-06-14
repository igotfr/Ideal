Operator | Method | Description | Types | Unary
:------: | :----: | :---------: | :---: | :---:
\+ | add() | Arithmetic addition | Integers, Bool, Floats, String, Array
\+= | add_assgn() | Arithmetic addition and assignment | Integers, Bool, Floats, String, Array
\+. | add() | Arithmetic Matrix Broadcast addition | Integers, Bool, Floats, String, Array
\+.= | add_assgn() | Arithmetic Matrix Broadcast addition and assignment | Integers, Bool, Floats, String, Array
\++ | conc() | Concatenation | Integers, Bool, Floats, String, Array
\- | sub() | Arithmetic subtraction | Integers, Bool, Floats
\- | neg() | Arithmetic negation | Integers, Bool, Floats | Unary
\-= | sub_assgn() | Arithmetic subtraction and assignment | Integers, Bool, Floats
\-. | sub() | Arithmetic Matrix Broadcast subtraction | Integers, Bool, Floats
\-. | neg() | Arithmetic Matrix Broadcast negation | Integers, Bool, Floats
\-.= | sub_assgn() | Arithmetic Matrix Broadcast subtraction and assignment | Integers, Bool, Floats
\* | mul() | Arithmetic multiplication | Integers, Floats, Bool, Array
\*= | mul_assgn() | Arithmetic multiplication and assignment | Integers, Bool, Floats, Array
\*. | mul() | Arithmetic Matrix Broadcast multiplication | Integers, Bool, Floats, String, Array
\*.= | mul_assgn() | Arithmetic Matrix Broadcast multiplication and assignment | Integers, Bool, Floats, String, Array
\** | repl() | Replication | Integers, Bool, Floats, String, Array
\/ | div() | Arithmetic division | Integers, Bool, Floats
\/= | div_assgn() | Arithmetic division and assignment | Integers, Bool, Floats
\/. | div() | Arithmetic Matrix Broadcast division | Integers, Bool, Floats, String, Array
\/.= | div_assgn() | Arithmetic Matrix Broadcast division and assignment | Integers, Bool, Floats, String, Array
\% | rem() | Arithmetic remainder | Integers, Bool, Floats
\%= | rem_assgn() | Arithmetic remainder and assignment | Integers, Bool, Floats
\%. | rem() | Arithmetic Matrix Broadcast remainder | Integers, Bool, Floats, String, Array
\%.= | rem_assgn() | Arithmetic Matrix Broadcast remainder and assignment | Integers, Bool, Floats, String, Array
\^ | pow() | Arithmetic potentiation | Integers, Bool, Floats
\^= | pow_assgn() | Arithmetic potentiation and assignment | Integers, Bool, Floats
\^. | pow() | Arithmetic Matrix Broadcast potentiation | Integers, Bool, Floats, String, Array
\^.= | pow_assgn() | Arithmetic Matrix Broadcast potentiation and assignment | Integers, Bool, Floats, String, Array
\! | fact() | Arithmetic factorial | Integers, Bool, Floats | Unary
\!. | fact() | Arithmetic Matrix Broadcast factorial | Integers, Bool, Floats, String, Array | Unary
\<< | shl() | Left bit shift | Integers, Bool
\<<= | shl_assgn() | Left bit shift and assignment | Integers, Bool
\>> | shr() | Right bit shift | Integers, Bool
\>>= | shr_assgn() | Right bit shift and assignment | Integers, Bool
\& and_bit | and_bit() | Bitwise AND | Integers, Bool
\&= | and_bit_assgn() |  Bitwise AND and assignment | Integers, Bool
\&& and | and() | Logical AND | short-circuit
\&. and | and() | Matrix Broadcast Logical AND | short-circuit
\& intersection | intersection() | Intersection
\| or_bit | or_bit() | Bitwise OR | Integers, Bool
\|= | or_bit_assgn() |  Bitwise OR and assignment | Integers, Bool
\|\| or | or() | Logical OR | short-circuit
\|. or | or() | Matrix Broadcast Logical OR | short-circuit
\| union | union() | union
\# xor_bit | xor_bit() | Bitwise XOR | Integers, Bool
\#= | xor_bit_assgn() |  Bitwise XOR and assignment | Integers, Bool
\~ and_bit | not_bit() | Bitwise NOT | Integers, Bool | Unary
\! ~ $ not | not() | Logical NOT | Integers, Bool | Unary
\== | eq() | Structural Equality
is | is() | Identity Equality
\!= ~= | ne() | Structural Non-equality
isnt | isnt() | Identity Non-equality
\< | lt() | Less than
\<= | le() | Less than or equal
\> | gt() | Greater than
\>= | ge() | Greater than or equal
