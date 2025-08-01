`Expires` 和 `Cache-Control` 都是 HTTP 协议中用于控制网页缓存的响应头。

**Expires**  
`Expires` 指定资源过期的具体时间点（GMT 时间）。
在该时间之前，浏览器会直接使用本地缓存，不会向服务器发送请求。
缺点是服务器和客户端时间不一致时可能导致缓存失效。

**Cache-Control**  
`Cache-Control` 更加灵活，常用的指令有 `max-age`（资源在多少秒内有效）、`no-cache`（每次都要向服务器验证）、`no-store`（不缓存）。它优先级高于 `Expires`，现代浏览器主要使用 `Cache-Control`。

如果你希望当前页面的内容被缓存，可以在服务器响应头中设置：
```
Cache-Control: max-age=3600
```
这样浏览器会在一小时内直接使用缓存内容。如果希望内容不被缓存，可以设置：
```
Cache-Control: no-store
```


## 最佳实践

### 1. 静态资源

- 使用 `Cache-Control: max-age=<seconds>` 设置较长的缓存时间。
- 结合文件哈希或版本号，确保资源更新后客户端能获取最新版本。

### 2. 动态资源

- 使用 `Cache-Control: no-cache` 或 `must-revalidate`，确保每次请求都验证缓存有效性。

### 3. 敏感数据

- 使用 `Cache-Control: no-store`，禁止缓存敏感数据。
