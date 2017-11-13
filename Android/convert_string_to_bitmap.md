# Convert String to Bitmap

is very simple.

just use :

```
byte[] decodedString = Base64.decode(base64Image, Base64.DEFAULT);
Bitmap decodedByte = BitmapFactory.decodeByteArray(decodedString, 0, decodedString.length);
```
