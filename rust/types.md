# Data Types

### Compound Types

**Tuple**

A tuple is a general way of grouping a values with a variety of types into one.
They have a fixed length. Once declared, they cannot grow or shrink.

e.g. `let tup: (i32, f64, u8) = (500, 6.4, 1);`

You can deconstruct them through pattern matching like so: `let (x, y, z) = tup;`
Then you can access the individual values.
You can also use dot notation followed by the index: `tup.0`.

**Arrays**

Arrays must be of the same type. They are also fixed length.
Declare like JS: `let a = [1, 2, 3, 4, 5];`. Index using bracket notation. `a[0]`

Arrays are useful when you want data allocated on the stack instead of the heap,
or to ensure you always have a fixed number of elements.

The vector type is the std library implementation of a collection that grows and shrinks.
