##### 1. pre-increment and post-increment
    * `++i` vs `i++`
    * `Array[++i]` vs `Array[i++]`

##### 2. short-circuiting
    * meaning they don't evaluate the right-hand side if it isn't necessary.
    * The &= operator is a shorthand for x = x & expression, and therefore is does NOT short circuit. The same is true of the |= operator.
    * `|` and `&` are binary operators, while `&&` and `||` are conditional (logical) operators. `|` and `&` work on more than just booleans, while `&&` and `||` work only on booleans.

写题的时候踩得大坑，最终才发现原来是因为logic operation的顺序，通过搜索知道了这个情况叫做short-circuiting。

##### 3. If a value is greater than the maximum `int` value 2^31 - 1, it overflows to a negative value. In Java, it would trigger an exception of `ArrayIndexOutOfBoundsException`.
    * Integers in Java are represented in 2’s complement binary and each integer gets 32 bits of space.
    * Integer.MAX_VALUE --> 2^31 - 1 = 2147483647
    * Integer.MIN_VALUE --> -2^31 = -2147483648

    * Integer.MAX_VALUE + 1 = -2147483648
    * Integer.MIN_VALUE - 1 = 2147483647