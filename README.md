# libalm
**libalm** is a fast arbitrary-precision / bignum mathematics library written in pure Zsh. It is designed for use anywhere a signed 64-bit integer just isn't big enough.
## Table of Contents
 * Arithmetic Functions
 * Conversion Functions
 * Logic Functions
## Arithmetic Functions
| Command | Arguments | Description |
|---|---|---|
| **alcm** | <num1> <num2> | **Comparator.** Returns 1 if num1 is larger, 2 if num2 is larger, or 3 if they are the same size. |
| **alia** | <num1> <num2> <outvar> | **Integer Adder.** Result is stored under $<outvar>. |
| **alis** | <num1> <num2> <outvar> | **Integer Subtraction.** Wrapper for alia which inverts the pos/neg sign of num2. |
| **alfa** | <num1> <num2> <outvar> | **Float Adder.** Result is stored under $<outvar>. |
| **alfs** | <num1> <num2> <outvar> | **Float Subtraction.** Wrapper for alfa which inverts the pos/neg sign of num2. |
| **alim** | <num1> <num2> <outvar> | **Integer Multiplier.** Result is stored under $<outvar>. |
| **almo** | <num1> <num2> <outvar> | **Modulo.** Runs alim, and stores the remainder under $<outvar>. |
| **alfm** | <num1> <num2> <outvar> | **Float Multiplier.** Result is stored under $<outvar>. |
| **alid** | <num1> <num2> <outvar> | **Integer Divider.** Result is stored under $<outvar>. Remainder is stored under $al_rem. |
| **alfd** | <num1> <num2> <outvar> | **Float Divider.** Result is stored under $<outvar>. *Note: Set the variable $al_scale to change precision (defaults to 20 decimal places).* |
## Conversion Functions
| Command | Arguments | Description |
|---|---|---|
| **dat2bin** | <data> <outvar> | Converts raw binary data to ASCII binary representation. |
| **bin2dat** | <binary> <outvar> | Converts ASCII binary representation to raw binary data. |
| **bin2hex** | <binary> <outvar> | Converts ASCII binary representation to hexadecimal. |
| **hex2bin** | <hex> <outvar> | Converts hexadecimal to ASCII binary representation. |
| **bin2dec** | <binary> <outvar> | Converts ASCII binary representation to a decimal value. |
| **dec2bin** | <dec> <outvar> | Converts a decimal value to ASCII binary representation. |
| **hex2dec** | <hex> <outvar> | Converts a hexadecimal value to a decimal value. |
| **dec2hex** | <dec> <outvar> | Converts a decimal value to a hexadecimal value. |
*(All conversion results are stored under $<outvar>)*
## Logic Functions
> **💡 Note on strmod:** With the exception of albm, all logic functions below support the strmod flag. When set to a non-empty value, the function expects raw data input instead of numeric input (allowing you to, for instance, XOR the strings "cat" and "dog").
> 
| Command | Arguments | Description |
|---|---|---|
| **albm** | <num> <mask> <outvar> | **Bitmask.** Applies <mask> to <num>. Set <hexmask> to non-empty to treat <mask> as a hex value. |
| **lrot** | <str> <count> <outvar> | **Left Rotate.** Strips 1 bit from the left side of <str> and appends it. Repeats <count> times. |
| **rrot** | <str> <count> <outvar> | **Right Rotate.** Strips 1 bit from the right side of <str> and prepends it. Repeats <count> times. |
| **lshft** | <str> <count> <outvar> | **Left Shift.** Strips 1 bit from the left side of <str> and appends a 0. Repeats <count> times. |
| **rshft** | <str> <count> <outvar> | **Right Shift.** Strips 1 bit from the right side of <str> and prepends a 0. Repeats <count> times. |
| **alxor** | <str1> <str2> <outvar> | **Bitwise XOR.** Performs bit-for-bit comparison (shortest string is left-padded with 0s). Writes 0 for like bit pairs, 1 for unlike. |
| **alxnor** | <str1> <str2> <outvar> | **Bitwise XNOR.** Bit-for-bit comparison. Writes 1 for like bit pairs, 0 for unlike. |
| **aland** | <str1> <str2> <outvar> | **Bitwise AND.** Bit-for-bit comparison. Writes 1 if both bits are 1, and 0 otherwise. |
| **alor** | <str1> <str2> <outvar> | **Bitwise OR.** Bit-for-bit comparison. Writes 1 if either bit is 1, and 0 otherwise. |
| **alnor** | <str1> <str2> <outvar> | **Bitwise NOR.** Bit-for-bit comparison. Writes 1 if both bits are 0, and 0 otherwise. |
| **alnand** | <str1> <str2> <outvar> | **Bitwise NAND.** Bit-for-bit comparison. Writes 1 if either bit is 0, and 0 otherwise. |
| **alnot** | <str> <outvar> | **Bitwise NOT.** Inverses the string (every 1 becomes a 0, every 0 becomes a 1). |
*(All logic results are stored under $<outvar>)*
