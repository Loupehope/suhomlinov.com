Чтобы добавить SOCKS прокси в iOS-приложение достаточно поправить конфигурацию URLSeesion:

```swift
let configuration: URLSessionConfiguration = .default
let proxyConfiguration: [AnyHashable: Any] = [
  "SOCKSEnabled": 1,
  "SOCKSProxy": "00.00.00.00", // ip-адрес прокси-сервера
  "SOCKSPort": 0000 // Порт прокси-сервера
]

configuration.connectionProxyDictionary = proxyConfiguration

let session: URLSession = .init(configuration: configuration)
```

Аналогично можно добавить HTTPS прокси только надо исползьовать следующие ключи: `HTTPSEnabled`, `HTTPSProxy`, `HTTPSPort`.
