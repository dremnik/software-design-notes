# Variables and Mutability

**Variables are immutable by default**
This means that if you were to try
```
let x = 5;
println!("the value of x is {}", x);
x = 6;
println!("the value of x is {}", x);
```
that you would get an error. You have to use `let mut x = 5` to get a mutable variable.

**Differences between variables and constants**
You aren't allowed to use *mut* with constants.
The type of a constant *must* be annotated. `const MAX_POINTS: u32 = 100_000;`

**Shadowing**
You can declare variables with the same name as previous variables using the let keyword.
Keep in mind that you are actually creating a new variable, it just has the same name.
Shadowing spares us from having to come up with different variable names.
