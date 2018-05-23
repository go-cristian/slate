# Setup

> To configure your token:

```xml
<meta-data
      android:name="com.pager.sdk.ApiKey"
      android:value="@string/your_api_key"/>
```

> To initialize, use this code:

```kotlin
override public fun onCreate(savedInstanceState: Bundle){
    ...
    Pager.init(this)
    ...
}
```

```java
@Override public void onCreate(Bundle savedInstanceState){
    ...
    Pager.init(this);
    ...
}
```

Pager uses an initialization step to make the SDK ready for their use, ypu need to modify your Android Manifest for this and initialize with a context (Application or Activity)