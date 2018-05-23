# Views

### Chat

```kotlin
class ChatActivity : AppCompatActivity() {

  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity)
    supportFragmentManager?
        .beginTransaction()
        .replace(R.id.container, ChatFragment.newInstance())
        .commitAllowingStateLoss()
  }
}
```
This is the main view of the app.

![Chat View](images/chat.png)

<aside class="success">
Remember — for letting Chat History know where is your Chat View located you need add the meta info of the Activity that it contains it
</aside>

### Chat History

```kotlin
class ChatHistoryActivity : AppCompatActivity() {

  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity)
    supportFragmentManager?
        .beginTransaction()
        .replace(R.id.container, TriageHistoryFragment.newInstance())
        .commitAllowingStateLoss()
  }
}
```
Chat history view, with detail.
![Chat History View](images/history.png)

### Payments

```kotlin
class ChatHistoryActivity : AppCompatActivity() {

  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity)
    supportFragmentManager?
        .beginTransaction()
        .replace(R.id.container, PaymentFragment.newInstance())
        .commitAllowingStateLoss()
  }
}
```
Payment screen.
![Payment View](images/payment.png)

### Promotions

```kotlin
class ChatHistoryActivity : AppCompatActivity() {

  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity)
    supportFragmentManager?
        .beginTransaction()
        .replace(R.id.container, PromotionsFragment.newInstance())
        .commitAllowingStateLoss()
  }
}
```
Promo codes.
![Promotions View](images/promo.png)

### Appointments List

```kotlin
class ChatHistoryActivity : AppCompatActivity() {

  override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity)
    supportFragmentManager?
        .beginTransaction()
        .replace(R.id.container, AppointmentsFragment.newInstance())
        .commitAllowingStateLoss()
  }
}
```
Appointments past/incoming.
![Appointments View](images/appointments.png)