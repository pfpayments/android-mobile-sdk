## API reference

| API | Type | Description |
| --- | :-: | --- |
| `PostFinanceCheckoutSdk.init(listener: OnResultEventListener)` | function | Initializes the SDK and registers the result listener. Must be called before using `PostFinanceCheckoutSdk.instance`. |
| `PostFinanceCheckoutSdk.instance` | singleton | Shared SDK instance used for configuration and launching payments. |
| `OnResultEventListener` | interface | Interface for handling post-payment events (`paymentResult`). |
| `fun paymentResult(paymentResult: PaymentResult)` | function | Callback invoked when transaction state changes or payment is completed. |
| `PostFinanceCheckoutSdk.instance?.launch(token: String, context: Context)` | function | Opens the payment flow. |
| `PostFinanceCheckoutSdk.instance?.launch(token: String, context: Context, paymentMethodConfigurationId: Int? = null)` | function | Opens the payment flow. `paymentMethodConfigurationId` is optional and can be used to preselect a payment method. |
| `PostFinanceCheckoutSdk.instance?.setDarkTheme(theme: JSONObject)` | function | Overrides or extends the default dark theme colors. |
| `PostFinanceCheckoutSdk.instance?.setLightTheme(theme: JSONObject)` | function | Overrides or extends the default light theme colors. |
| `PostFinanceCheckoutSdk.instance?.setCustomTheme(theme: JSONObject?, baseTheme: ThemeEnum)` | function | Forces a custom theme regardless of system appearance. Missing values are merged with the selected base theme. |
| `PostFinanceCheckoutSdk.instance?.setAnimation(type: AnimationEnum)` | function | Sets transition animation style used inside the payment flow. |
| `PostFinanceCheckoutSdk.instance?.setPendingTimeout(sec: Int)` | function | Sets how long (in seconds) the SDK keeps polling the backend for a final transaction status when the customer aborts an external payment step, before returning `PENDING`. The SDK polls every 2 seconds. The value is clamped between `2` and `600` seconds (10 minutes). When not set, the SDK returns `PENDING` immediately. |
| `PostFinanceCheckoutSdk.instance?.SDK_VERSION` | property | Current SDK version. |
