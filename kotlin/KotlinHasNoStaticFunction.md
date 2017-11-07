# Kotlin has No Static Function

So every class has a instance and use the method.

but can use __companion object__ to get the same effect as static functions.

such as : 

```
class Foo {
  companion object {
     fun a() : Int = 1
  }
}
```
