# Integrations

## Google Calendar API

LeadsCalendar leverages the Google Calendar API to enable users to directly create events within the application.

```curl
POST https://www.googleapis.com/calendar/v3/calendars/calendarId:string/events
```

- required path parameter: calendarId
- header: Authorization: Bearer [YOUR_ACCESS_TOKEN]
- header: content-type

```json
{
  "end": {},
  "start": {}
}
```

For more information visit the [official documentation](https://developers.google.com/calendar/api/v3/reference/events/insert)

## PayPal API

LeadsCalendar leverages the PayPal REST API to provide a secure payment processing option for users.

```curl
POST https://api-m.paypal.com/v2/checkout/orders/{id}/authorize
```

- required path parameter: id
- header: Authorization: Bearer [YOUR_ACCESS_TOKEN]
- header: PayPal-Request-Id
- header: content-type

For more information visit the [official documentation](https://developer.paypal.com/docs/api/orders/v2/#orders_authorize)

## Binance API

LeadsCalendar leverages Binance Pay to provide users with an alternative for making payments using cryptocurrency.

Build the content:

```java
String payload = timestamp + "\n" + nonce + "\n" + body + "\n";
```

```curl
POST https://bpay.binanceapi.com
```

- header: PayPal-Request-Id
- header: content-type
- header: BinancePay-Timestamp
- header: BinancePay-Nonce
- header: BinancePay-Certificate-SN
- header: BinancePay-Signature

Sign the content

```java
String signature = hex(hmac("sha512", payload, secretKey)).toUpperCase()
```

For more information visit the [official documentation](https://developers.binance.com/docs/binance-pay/api-common)
