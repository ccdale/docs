[back](index.md)

# Mathematics for Encryption

## Integers

An integer is a whole number without a fractional part. 2, 234, 70689 are all
examples of integers.

23.754 is a floating point number as it has a fractional part, so therefore it
is not an integer.

## Integer Division and Mod

Integer division is the process whereby you can calculate the number of times
one integer is contained in another.  The result is always an integer, the
remainder is thrown away. 7 / 2 = 3 is an example the remainder of 1 is thrown
away.

Mod is the process of calculating the remainder part of an integer division. It
is usually denoted with the percent symbol.  Using the integer division example
above: 7 % 2 = 1.

## Power

The exponent of a number simply says how many times to multiply that number by
itself.  i.e. `5 ^ 2` says to multiply `5x5`, `3 ^ 4` says to multiply
`3x3x3x3`.  This process is called 'raising to the power of' (and in the case
where the exponent is 2 or 3 - 'squared' or 'cubed')

## Binary

Binary is a number system based on 2 (digits 0 - 1).  Our usual number system is based on 10
(digits 0 - 9).  As computer systems are mostly comprised of logic circuits that
have a one of two states - on or off, it is easy to translate numbers to binary
for usage in computers.

Just like in the 10s based system the extreme right hand side of a binary number
is the lowest value, increasing in value the further you move to the left.

the 10s based number `1079` is composed thus (starting at the right):
```
9 x 1    =    9
7 x 10   =   70
0 x 100  =    0
1 x 1000 = 1000
           ----
           1079
```

Similarly the binary number `1011001` is composed:
```
1 x 1  =  1
0 x 2  =  0
0 x 4  =  0
1 x 8  =  8
1 x 16 = 16
0 x 32 =  0
1 x 64 = 64
         --
         89
```
## Boolean Logic

Boolean operators operate at the bit level so binary is an ideal number format when numbers are being manipulated with Boolean
Logic.

### Not Operator

One input, one output.  The output is the inverse of the input.

|        |   |   |
|--------|--:|--:|
| input  | 0 | 1 |
| output | 1 | 0 |


### And Operator

Two inputs, one output. The output is 1 if both the inputs are one, else it is zero

|         |   |   |   |   |
|---------|--:|--:|---|---|
| input a | 0 | 0 | 1 | 1 |
| input b | 0 | 1 | 0 | 1 |
| output  | 0 | 0 | 0 | 1 |

### Or Operator

Two inputs, one output. The output is 1 if either or both the inputs are one, else it is zero

|         |   |   |   |   |
|---------|--:|--:|---|---|
| input a | 0 | 0 | 1 | 1 |
| input b | 0 | 1 | 0 | 1 |
| output  | 0 | 1 | 1 | 1 |

### Xor Operator

Exclusive Or with two inputs, one output. The output is 1 if one of the inputs is 1 and the other is zero, else the output is
zero. With a little thought you will see that this operator is important in encryption as it is completely reversible. Xor the
output with one of the inputs and you get the other input.

|         |   |   |   |   |
|---------|--:|--:|---|---|
| input a | 0 | 0 | 1 | 1 |
| input b | 0 | 1 | 0 | 1 |
| output  | 0 | 1 | 1 | 0 |


[back](index.md)
