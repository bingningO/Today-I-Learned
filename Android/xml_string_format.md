# Define String Format in xml

Here want to set a string in TextView like: "**Today** I'm happy!"

Althrough It can get the TextView and user [Spannable](https://developer.android.com/reference/android/text/Spannable.html), but a little complex.

just use 
```
<b>Today</b> I'm happy!
```
can realize it .

## a small summary  

* %s , for string
* %d , for data
* %1$s,%2$s, %1$d, %2$d , the 1$ or 2$ means the which one to use, like: 
```
//.xml
<?xml version="1.0" encoding="utf-8"?>  
<resources>  
    <string name="action">%1$s I eat 4 apples!</string>  
</resources>  

//.java
String buybooks = getString(R.string.action, "Today"); 

// result
"Today I eat 4 apples!"

/************************************************
************************************************/
//.xml
<?xml version="1.0" encoding="utf-8"?>  
<resources>  
    <string name="action">%1$s I eat %2$d apples!</string>  
</resources>  

//.java
String buybooks = getString(R.string.action, "Tomorrow", 2); 

// result
"Tomorrow I eat 2 apples!"
```
* special format(also can use in Markdown) : <b><i><u>
```
<b>bold text</b>
<i>italic text</i>
<u>underline text</u>
// p.s. but notice that this format can't be previewed in Android Studio. 
```
