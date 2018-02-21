# The Difference in const, val and var

1. var
```
var temple = 0
var temple: String // don't need to initialize
lateinit var temple: String // class-level value, initialized when firstly used, can be non-null 
```

2. val
```
val temple = 100
```
is like **final**, once assigned can't change again.

3. const var in companion object
```
componion object {
　　const var TEMPLE = 100
  }
```
to see the kotlin Bytecode, it's like **public static final int ...**</br>
if you want private static final...</br>
just define it as 
```
componion object {
　　private const var TEMPLE = 100
  }
```

as **static**, this value will be assigned in *compile-time*. Not like other values all be assigned in *run-time* 
