---
id: data_types
title: Data Types
sidebar_label: Data Types
---

All constants, variables, functions and expressions have an associated type. BlitzMax supports the following types:

|  Description | Syntax  | Minimum value  |  Maximum value |
|---|---|---|---|
| 8 bit unsigned integer | [Byte] | 0  | 255  |
| 16 bit unsigned integer |  [Short] | 0  | 65535  |
| 32 bit signed integer | [Int]  |  -2^31 | +2^31-1  |
| 32 bit unsigned integer |  [UInt] |  0 |  +2^32-1 |
| 64 bit signed integer |  [Long] | -2^63  | +2^63-1  |
| 64 bit unsigned integer | [ULong]  | 0  | +2^64-1  |
| 32 bit floating point  | [Float]  | (+/-)10^-38  | (+/-)10^38  |
| 64 bit floating point  | [Double]  | (+/-)10^-308  | (+/-)10^308  |
| 16 bit unicode string  | [String]  |   |   |
| Unsigned integer (32 bit arch)  | [Size_T]  | 0  | +2^32-1  |
| Unsigned integer (64 bit arch)  | [Size_T]  | 0  | +2^64-1  |
| 64 bit SIMD float  | [Float64]  |   |   |
| 128 bit SIMD integer  | [Int128]  |   |   |
| 128 bit SIMD float  | [Float128]  |   |   |
| 128 bit SIMD double  | [Double128]  |   |   |
| Object  | Typename  |   |   |
| Array  | ElementType [ ]  |   |   |
| Function  | ReturnType ( Parameters )  |   |   |
| Pointer  | ValueType Ptr  |   |   |
| Variable  | VariableType Var  |   |   |

Integers are used to store simple numeric data without any fractional part.
Unsigned integers can only store positive values, while signed integers can store both positive and negative values.

Floating point values are used to store numeric data which may have a fractional part.

SIMD values are available on x64 architectures and can be used for performing numeric calculations more efficiently.

Strings are used to store sequences of characters: letters, punctuation, digits and so on. Use strings for storing
non-numeric data such as names.

Arrays are used to store sequences of variables. A variable within an array is accessed by 'indexing' the array with an
integer offset. Please refer to the arrays sections for more information on arrays.

Objects are instances of user-defined types. Please refer to the user-defined types section.

## Type Conversions

The following type conversions are performed automatically by BlitzMax when necessary - for example, when assigning an
expression to a variable, or when passing an expression to a function:

| Source Type  | Target Type  |
|---|---|
| Integer  | Floating point, String  |
| Floating point | String  |

You can also convert types explicitly using a cast operation. This takes the form of a type specifier followed by an
expression in brackets.

Explicit casting allows you to perform the following extra conversions:

| Source Type  | Target Type  |
|---|---|
| String  | Integer, Floating point  |

For example:

```blitzmax
Local n:Int=10
Local t:String="20"
Print Int( t )
Print String( n )
```
## Type Balancing

When performing arithmetic operations such as addition or multiplication, it is possible to provide mismatched argument
types. For example, the addition operator may be used to add an integer value to a floating point value. But what type
should the result be?

BlitzMax decides the result type by balancing the argument types. Both arguments are then converted to the result type
before the operator is applied.

The rules governing type balancing are:



> If either argument is [Double], then result is [Double]
>
> else if either argument is [Float], then result is [Float]
>
> else if either argument is [ULong], then result is [ULong]
>
> else if either argument is [Size_T], then result is [Size_T]
>
> else if either argument is [WParam], then result is [WParam]
>
> else if one argument is [Long] and the other [UInt], then result is [ULong]
>
> else if either argument is [LParam], then result is [LParam]
>
> else if either argument is [Long], then result is [Long]
>
> else if either argument is [UInt], then result is [UInt]
>
> else result is [Int]

[Byte]: ../../api/brl/brl.blitz/#byte
[Short]: ../../api/brl/brl.blitz/#short
[Int]: ../../api/brl/brl.blitz/#int
[UInt]: ../../api/brl/brl.blitz/#uint
[Long]: ../../api/brl/brl.blitz/#long
[ULong]: ../../api/brl/brl.blitz/#ulong
[Float]: ../../api/brl/brl.blitz/#float
[Double]: ../../api/brl/brl.blitz/#double
[String]: ../../api/brl/brl.blitz/#string
[Size_T]: ../../api/brl/brl.blitz/#size_t
[Float64]: ../../api/brl/brl.blitz/#float64
[Int128]: ../../api/brl/brl.blitz/#int128
[Float128]: ../../api/brl/brl.blitz/#float128
[Double128]: ../../api/brl/brl.blitz/#double128
[LParam]: ../../api/brl/brl.blitz/#lparam
[WParam]: ../../api/brl/brl.blitz/#wparam
