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
| `PostFinanceCheckoutSdk.instance?.SDK_VERSION` | property | Current SDK version. |
