also in Java there has *AtomicInterget*

[simple refer](https://www.geeksforgeeks.org/atomicinteger-getandset-method-in-java-with-examples/)

it can be used as some count number

```
// initial , temp = 0
val temp = AtomicInterger()

// firstly give value, then update
// res = 0, temp = 10
val res = temp.getAndSet(10)

// increse 1 to temp, temp = 11
temp.incrementAndGet()
```
