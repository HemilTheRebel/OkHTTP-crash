# Ok HTTP failing on Android 11 Minimal, Viable Example


The current version of the project is using OkHTTP 4.1.0. 
Upgrading to 4.2.0 to 4.4.0 works and I recommend using whatever latest
version that supports all API versions you intent to support
 

Running the app crashes with this error:
```
E/AndroidRuntime: FATAL EXCEPTION: main
    Process: com.example.okhttptest, PID: 12713
    java.lang.ExceptionInInitializerError
        at okhttp3.OkHttpClient.<init>(OkHttpClient.kt:219)
        at okhttp3.OkHttpClient.<init>(OkHttpClient.kt:211)
        at com.example.okhttptest.MainActivity.<init>(MainActivity.java:15)
        at java.lang.Class.newInstance(Native Method)
        at android.app.AppComponentFactory.instantiateActivity(AppComponentFactory.java:95)
        at androidx.core.app.CoreComponentFactory.instantiateActivity(CoreComponentFactory.java:45)
        at android.app.Instrumentation.newActivity(Instrumentation.java:1253)
        at android.app.ActivityThread.performLaunchActivity(ActivityThread.java:3353)
        at android.app.ActivityThread.handleLaunchActivity(ActivityThread.java:3601)
        at android.app.servertransaction.LaunchActivityItem.execute(LaunchActivityItem.java:85)
        at android.app.servertransaction.TransactionExecutor.executeCallbacks(TransactionExecutor.java:135)
        at android.app.servertransaction.TransactionExecutor.execute(TransactionExecutor.java:95)
        at android.app.ActivityThread$H.handleMessage(ActivityThread.java:2066)
        at android.os.Handler.dispatchMessage(Handler.java:106)
        at android.os.Looper.loop(Looper.java:223)
        at android.app.ActivityThread.main(ActivityThread.java:7656)
        at java.lang.reflect.Method.invoke(Native Method)
        at com.android.internal.os.RuntimeInit$MethodAndArgsCaller.run(RuntimeInit.java:592)
        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:947)
     Caused by: java.lang.IllegalStateException: Expected Android API level 21+ but was 30
        at okhttp3.internal.platform.AndroidPlatform$Companion.buildIfSupported(AndroidPlatform.kt:370)
        at okhttp3.internal.platform.Platform$Companion.findPlatform(Platform.kt:204)
        at okhttp3.internal.platform.Platform$Companion.access$findPlatform(Platform.kt:178)
        at okhttp3.internal.platform.Platform.<clinit>(Platform.kt:179)
        at okhttp3.OkHttpClient.<init>(OkHttpClient.kt:219) 
        at okhttp3.OkHttpClient.<init>(OkHttpClient.kt:211) 
        at com.example.okhttptest.MainActivity.<init>(MainActivity.java:15) 
        at java.lang.Class.newInstance(Native Method) 
        at android.app.AppComponentFactory.instantiateActivity(AppComponentFactory.java:95) 
        at androidx.core.app.CoreComponentFactory.instantiateActivity(CoreComponentFactory.java:45) 
        at android.app.Instrumentation.newActivity(Instrumentation.java:1253) 
        at android.app.ActivityThread.performLaunchActivity(ActivityThread.java:3353) 
        at android.app.ActivityThread.handleLaunchActivity(ActivityThread.java:3601) 
        at android.app.servertransaction.LaunchActivityItem.execute(LaunchActivityItem.java:85) 
        at android.app.servertransaction.TransactionExecutor.executeCallbacks(TransactionExecutor.java:135) 
        at android.app.servertransaction.TransactionExecutor.execute(TransactionExecutor.java:95) 
        at android.app.ActivityThread$H.handleMessage(ActivityThread.java:2066) 
        at android.os.Handler.dispatchMessage(Handler.java:106) 
        at android.os.Looper.loop(Looper.java:223) 
        at android.app.ActivityThread.main(ActivityThread.java:7656) 
        at java.lang.reflect.Method.invoke(Native Method) 
        at com.android.internal.os.RuntimeInit$MethodAndArgsCaller.run(RuntimeInit.java:592) 
        at com.android.internal.os.ZygoteInit.main(ZygoteInit.java:947) 
I/Process: Sending signal. PID: 12713 SIG: 9
```