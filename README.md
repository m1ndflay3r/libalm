*libalm* is an arbitrary-precision / bignum mathematics library written in pure zsh, for use anywhere a signed 64-bit int just isnt big enough.


Usage:


    alcm <num1> <num2>
Comparator. Returns 1 if num1 is larger, 2 if num2 is larger, or 3 if they're the same size.

    alia <num1> <num2> <outvar>
Integer adder. Result is stored under $<outvar>.

    alis <num1> <num2> <outvar>
Wrapper for alia which inverts pos/neg sign of num2 (subtraction).

    alfa <num1> <num2> <outvar>
Float adder. Result is stored under $<outvar>.

    alfs <num1> <num2> <outvar>
Wrapper for alfa which inverts pos/neg sign of num2 (subtraction).

    alim <num1> <num2> <outvar>
Integer multiplier. Result is stored under $<outvar>.

    almo <num1> <num2> <outvar>
Modulo. Runs alim, and stores remainder under $<outvar>.

    alfm <num1> <num2> <outvar>
Float multiplier. Result is stored under $<outvar>.

    alid <num1> <num2> <outvar>
Integer divider. Result is stored under $<outvar>.

    alfd <num1> <num2> <outvar>
Float divider. Result is stored under $<outvar>.
