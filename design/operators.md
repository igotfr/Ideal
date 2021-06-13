Operator | Method | Description | Types | Unary
:------: | :----: | :---------: | :---: | :---:
\+ | add() | Arithmetic addition | Integers, Floats, Bool, Array
\+= | add_assgn() | Arithmetic addition and assignment | Integers, Floats, Bool, Array
\+. | add() | Arithmetic Matrix Broadcast addition | Integers, Floats, Array
\+.= | add_assgn() | Arithmetic Matrix Broadcast addition and assignment | Integers, Floats, Array
\++ | conc() | Concatenation | Integers, Floats, String, Array
\- | sub() | Arithmetic subtraction
\- | neg() | Arithmetic negation | | Unary
\-= | sub_assgn() | Arithmetic subtraction and assignment
\-. | sub() | Arithmetic Matrix Broadcast subtraction
\-. | neg() | Arithmetic Matrix Broadcast negation
\-.= | sub_assgn() | Arithmetic Matrix Broadcast subtraction and assignment
\* | mul() | Arithmetic multiplication | Integers, Floats, Bool, Array
\*= | mul_assgn() | Arithmetic multiplication and assignment | Integers, Floats, Bool, Array
\*. | mul() | Arithmetic Matrix Broadcast multiplication | Integers, Floats, Array
\*.= | mul_assgn() | Arithmetic Matrix Broadcast multiplication and assignment | Integers, Floats, Array
\** | repl() | Replication | Integers, Floats, String, Array
\/ | div() | Arithmetic division
\/= | div_assgn() | Arithmetic division and assignment
\/. | div() | Arithmetic Matrix Broadcast division
\/.= | div_assgn() | Arithmetic Matrix Broadcast division and assignment
\% | rem() | Arithmetic remainder
\%= | rem_assgn() | Arithmetic remainder and assignment
\%. | rem() | Arithmetic Matrix Broadcast remainder
\%.= | rem_assgn() | Arithmetic Matrix Broadcast remainder and assignment
\^ | pow() | Arithmetic potentiation
\^= | pow_assgn() | Arithmetic potentiation and assignment
\^. | pow() | Arithmetic Matrix Broadcast potentiation
\^.= | pow_assgn() | Arithmetic Matrix Broadcast potentiation and assignment
\! | fact() | Arithmetic factorial | | Unary
\!. | fact() | Arithmetic Matrix Broadcast factorial | | Unary
\<< | shl() | Left bit shift
\<<= | shl_assgn() | Left bit shift and assignment
\>> | shr() | Right bit shift
\>>= | shr_assgn() | Right bit shift and assignment
\& and_bit | and_bit() | Bitwise AND
\&= | and_bit_assgn() |  Bitwise AND and assignment
\&& and | and() | Logical AND
\&. and | and() | Matrix Broadcast Logical AND
\& intersection | intersection() | Intersection
\| or_bit | or_bit() | Bitwise OR
\|= | or_bit_assgn() |  Bitwise OR and assignment
\|\| or | or() | Logical OR
\|. or | or() | Matrix Broadcast Logical OR
\| union | union() | union
\# xor_bit | xor_bit() | Bitwise XOR
\#= | xor_bit_assgn() |  Bitwise XOR and assignment
\~ and_bit | not_bit() | Bitwise NOT | | Unary
\! ~ $ not | not() | Logical NOT | | Unary
\== | eq() | Structural Equality
is | is() | Identity Equality
\!= ~= | ne() | Structural Non-equality
isnt | isnt() | Identity Non-equality
\< | lt() | Less than
\<= | le() | Less than or equal
\> | gt() | Greater than
\>= | ge() | Greater than or equal
