# A Goodway for Adding timeout in Asyntask

```
final SampleTask task = new SampleTask();
task.execute();

// TimeOut処理
new Thread(new Runnable() {
    @Override
    public void run() {
        try {
            // TimeOutに10秒を指定
            // 10秒以内にTaskが終了しなければTimeoutExceptionを投げる
            task.get(10000, TimeUnit.MILLISECONDS);
        } catch (Exception e) {
            // Exceptionをキャッチしtaskをキャンセルする
            task.cancel(true);
            e.printStackTrace();
        }
    }
}).start();
```

be aware that asyntask.get(....) would bloke UI thread, so need to add new Thread(Runnable...)
but if the asyntask has already in a sub-thread, then don't need to worry about blocking UI thread, </br>
directly using **get(...)** and **try{...} catch(TimeoutException e)** is OK.
