**libalm** is a fast arbitrary-precision / bignum mathematics library written in pure zsh, for use anywhere a signed 64-bit integer just isnt big enough.


----------------------


__arithmetic functions:__



    alcm <num1> <num2>
Comparator. Returns 1 if num1 is larger, 2 if num2 is larger, or 3 if they're the same size.

    alia <num1> <num2> <outvar>
Integer adder. Result is stored under $\<outvar\>.

    alis <num1> <num2> <outvar>
Wrapper for alia which inverts pos/neg sign of num2 (subtraction).

    alfa <num1> <num2> <outvar>
Float adder. Result is stored under $\<outvar\>.

    alfs <num1> <num2> <outvar>
Wrapper for alfa which inverts pos/neg sign of num2 (subtraction).

    alim <num1> <num2> <outvar>
Integer multiplier. Result is stored under $\<outvar\>.

    almo <num1> <num2> <outvar>
Modulo. Runs alim, and stores remainder under $\<outvar\>.

    alfm <num1> <num2> <outvar>
Float multiplier. Result is stored under $\<outvar\>.

    alid <num1> <num2> <outvar>
Integer divider. Result is stored under $\<outvar\>.

    alfd <num1> <num2> <outvar>
Float divider. Result is stored under $\<outvar\>.


----------------------


__conversion functions__


    dat2bin <data> <outvar>
Converts raw binary data to ASCII binary representation. Result is stored under $\<outvar\>.

    bin2dat <binary> <outvar>
Converts ASCII binary representation to raw binary data. Result is stored under $\<outvar\>.

    bin2hex <binary> <outvar>
Converts ASCII binary representation to hexadecimal. Result is stored under $\<outvar\>.

    hex2bin <hex> <outvar>
Converts hexadecimal to ASCII binary representation. Result is stored under $\<outvar\>.

    bin2dec <binary> <outvar>
Converts ASCII binary representation to decimal value. Result is stored under $\<outvar\>.

    dec2bin <dec> <outvar>
Converts decimal value to ASCII binary representation. Result is stored under $\<outvar\>.

    hex2dec <hex> <outvar>
Converts hexadecimal value to decimal value. Result is stored under $\<outvar\>.

    dec2hex <dec> <outvar>
Converts decimal value to hexadecimal value. Result is stored under $\<outvar\>.
