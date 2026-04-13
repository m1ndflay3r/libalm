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
Integer divider. Result is stored under $\<outvar\>. Remainder is stored under "$al_rem".

    alfd <num1> <num2> <outvar>
Float divider. Set variable "al_scale" to change precision (default 20 decimal places). Result is stored under $\<outvar\>.


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


----------------------


__logic functions__


    albm <num> <mask> <outvar>
Bitmask. Applies \<mask\> to \<num\> and assigns result to \<outvar\>. Set \<hexmask\> to non-empty to treat \<mask\> as a hex value.

    lrot <str> <count> <outvar>
Left rotate. Strips 1 bit from left side of \<str\> and appends it. Repeats this behavior \<count\> times. Result is stored under \<outvar\>.

    rrot <str> <count> <outvar>
Right rotate. Strips 1 bit from right side of \<str\> and prepends it. Repeats this behavior \<count\> times. Result is stored under \<outvar\>.

    lshft <str> <count> <outvar>
Left shift. Strips 1 bit from left side of \<str\> and appends a 0. Repeats this behavior \<count\> times. Result is stored under \<outvar\>.

    rshft <str> <count> <outvar>
Right shift. Strips 1 bit from right side of \<str\> and prepends a 0. Repeats this behavior \<count\> times. Result is stored under \<outvar\>.

    alxor <str1> <str2> <outvar>
Bitwise XOR. Takes two strings of any size (shortest is left padded with 0s), and performs bit for bit comparison, writing a 0 for every like bit pair and a 1 for every unlike bit pair. Stores result under \<outvar\>.

    alxnor <str1> <str2> <outvar>
Bitwise XNOR. Takes two strings of any size (shortest is left padded with 0s), and performs bit for bit comparison, writing a 1 for every like bit pair and a 0 for every unlike bit pair. Stores result under \<outvar\>.

    aland <str1> <str2> <outvar>
Bitwise AND. Takes two strings of any size (shortest is left padded with 0s), and performs bit for bit comparison, writing a 1 if both bits are 1 and a 0 otherwise. Stores result under \<outvar\>.

    alor <str1> <str2> <outvar>
Bitwise OR. Takes two strings of any size (shortest is left padded with 0s), and performs bit for bit comparison, writing a 1 if either bit is 1 and a 0 otherwise. Stores result under \<outvar\>.

    alnor <str1> <str2> <outvar>
Bitwise NOR. Takes two strings of any size (shortest is left padded with 0s), and performs bit for bit comparison, writing a 1 if both bits are 0 and a 0 otherwise. Stores result under \<outvar\>.

    alnand <str1> <str2> <outvar>
Bitwise NAND. Takes two strings of any size (shortest is left padded with 0s), and performs bit for bit comparison, writing a 1 if either bit is 0 and a 0 otherwise. Stores result under \<outvar\>.

    alnot <str> <outvar>
Bitwise NOT. Takes a string and writes its inverse (every 1 becomes a 0, every 0 a 1). Result is stored under <outvar>.




_note: with the exception of albm, all logic functions have the flag "strmod" which when set to a non-empty value results in expecting of raw data input instead of num (this would, for instance, allow you to xor "cat" and "dog")_
