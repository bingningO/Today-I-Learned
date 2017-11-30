# Data String Format

```
// the head all set by "0", the length is at least 5 
System.out.println(String.format("%05d", 1));
System.out.println(String.format("%05d", 123));
System.out.println(String.format("%05d", 123456));
 
// the head all set by " ", the length is at least 4 
System.out.println(String.format("%4d", 1));
System.out.println(String.format("%4d", 123));
System.out.println(String.format("%4d", 123456));
 
// the last all set by "0", the length is at least 4
System.out.print(String.format("%-4d", 1));
System.out.println("|");
System.out.print(String.format("%-4d", 123));
System.out.println("|");
System.out.print(String.format("%-4d", 123456));
System.out.println("|");
```

the result is : 
```
00001
00123
123456

   1
 123
123456

1   |
123 |
123456|
```
