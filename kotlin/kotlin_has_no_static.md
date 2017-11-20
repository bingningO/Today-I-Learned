# Kotlin has No Static Function and Value

So every class has a instance and use the method.

but can use __companion object__ to get the same effect as static functions.

1. static function

```
class Foo {
  companion object {
     @JvmStatic
     fun a() : Int = 1
  }
}
```

add  @JvmStatic to make the Java file can also directly use this function, like **Foo.a()** .</br>
or Java file need to change to **Foo.object.a()**

2. static value
```
class Foo {
  companion object {
     const val A = "here is A"
     const val B = "here is B"
  }
}
```
add *const* to make the Java file can also directly use this value, like **Foo.A**.</br>
or Java file need to change to **Foo.object.A**

