# Convert To Json

when converting data to Json 

it's weired that can't convert to Json orderly by **gson**

*ItemData.kt*
```
data class ItemData (
        var id : String,
        var name : String,
        var price : Float,
        var count : Int
)
```
*ConvertActivity.kt*
```
 val obj = ItemData("0001", "name", 0.05f, 2)
        val jsonObj = Gson().toJson(obj)
        Log.d(TAG, "item:$jsonObj")
```

but only get the result that (ordered by alphapet defautly)
> item:{"count":2,"id":"0001","name":"name","price":0.05}

it seems like **Gson.toJson(Object object)** generates JSON code with randomly spread fields of the object.

So it's better to use **jackson**</br>
(or define a custom JSON serializer.)

---
using **jackson** like below

*ItemData.kt*
```
@JsonPropertyOrder("id", "name", "price", "count")
data class ItemData (
        var id : String,
        var name : String,
        var price : Float,
        var count : Int
)
```
*ConvertActivity.kt*
```
val mapper = ObjectMapper()
        val obj = ItemData("0001", "name", 0.05f, 2)
        val jsonInString = mapper.writeValueAsString(obj)
        Log.d(TAG, "item:$jsonInString")
```

can get results as 
> item:{"id":"0001","name":"name","price":0.05,"count":2}
