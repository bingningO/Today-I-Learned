# Kotlin Extension v.s. ButterKnife

In my opinion, *extension* is definitely better than *Butterknife*</br>

simple sum up is: 
* very simpler to use
* effictive, even just slightly better
* smarter, *butterknife* should bind all the view at the same time. Which *extension* just call a **catching function** when needed.

BTW, there is not so much difference as JackWarthon has fixed Butterknife as can be used in kotlin, and kotlin extension also has a fix to be easily used in adapter-holder

here is the example:

firstly, sample.xml is the same.
```
<...>
    <View android:id="@+id/text_name" ... />
    <View android:id="@+id/text_password" ... />
</>
```

then in Butterknife, need to 
```
@BindView(R.id.text_name) lateinit var View textName
@BindView(R.id.text_password) lateinit var View textPsw

@OnClick(R.id.text_password) fun onClickTextPsw() {
// do something when click it 
}

// in onCreate() of Activity
override onCreate() {
...
 ButterKnife.bind(this)
}

// but in Fragment need to be unbind
private lateinit var unbinder: Unbinder

override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?, savedInstanceState: Bundle?): View? {
    ...
    unbinder = ButterKnife.bind(this, view)
    return view
}

override fun onDestroyView() {
    super.onDestroyView()
    unbinder.unbind()
}
```

and here is the use of kotlin extension</br>
directly call the id in .xml

```
// the simple use in Activity/Fragment 
text_name.text = "user name"
text_password.setOnClickListner {view ->
// do something when clicked
}

// the also simple use in adapter-holder
internal class Holder(baseView: View) {
val textName = baseView.text_name as View
val textPsw = baseView.text_password as View
}

override fun getView(...) {
val holder = Holder(convertView)
holder.textPsw.setOnClickListner{view ->
// do something when clicked
}
```

