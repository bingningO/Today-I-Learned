# when use case in Kotlin 

kotlin has when , is better convenient than java.

## when & return 
```
// boo : boolean
when (boo) {
   true -> return "boo is true"
   false -> return "boo is false"
}
```
or even better to use
```
// boo : boolean
return when (boo) {
   true -> "boo is true"
   false -> "boo is false"
}
```

## when & value 
```
// boo : boolean
var value = when (boo) {
   true -> 1
   false -> 0
}
```
