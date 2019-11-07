_view gone_ means taking off the view, the view don't take off any space 

_view insivible_ means the view can't be seen, but it still takes the space 

it's interesting that if u set view.gone after rotating the device, then set 
```
view.visibility = VISIBLE
view.x = 30F
```
would be weird , not the place u want to show. 


it's because after rotation the Android system calls *[onConfigurationChanged()](https://developer.android.com/guide/topics/resources/runtime-changes)*,
in fact you don't need to know what this method does, it just renew the views to adjust the new window size. (not call onResume(), etc.)

but if u set `view.visibility = GONE` at the *onConfigurationChanged()* and then set it visible again. 

the view would not be set to adjust the window size , so it's position would be weird (only this view's window size would still be the one before rotation). 

the best practise is just change `view.visibility = GONE` to `view.visibility = INVISIBLE`
