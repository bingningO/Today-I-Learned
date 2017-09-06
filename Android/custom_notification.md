# Custom Notification

## Nomal notification (small hight, 64dp)
```
// set a nomal notification with title, icon, text 
NotificationCompat.Builder mBuilder =
        new NotificationCompat.Builder(this)
        .setSmallIcon(R.drawable.notification_icon)
        .setContentTitle("My notification")
        .setContentText("Hello World!");
```

## Custom notification (with custom view)
```
// set Builder as above
// use RemoteViews as customView, althrough almost can do anything, better to be as simple as possible
RemoteViews customView = new RemoteViews(context.getPackageName(), R.layout.notification_layout);
builder.setContent(customView); // 64dp hight

builder.setBigContenView(customView); // the hight can up to 256dp
```
but be aware that the big content view __only shown as the first notification or unfolded manually__.

and Google recommends to __use the default style of background and text color__ as the Notification Background is different on different devices. Of course view like ImageView also should be careful with different backgroud color.

---
**Reference**:
[CustomNotification](https://developer.android.com/guide/topics/ui/notifiers/notifications.html?hl=ja#CustomNotification)
