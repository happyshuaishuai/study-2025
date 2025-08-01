浏览器 Cookie 是一种在客户端（用户浏览器）中存储少量数据的机制。它用于在用户与网站交互时保存状态信息，如登录状态、用户偏好设置等。每次浏览器向同一网站发送请求时，相关的 Cookie 会自动随请求发送到服务器，从而实现会话管理、个性化和跟踪等功能。Cookie 通常包含名称、值、过期时间、路径和域等属性。

Cookie就是存储在客户端的数据，用于区分用户身份和进行会话跟踪。

## Cookie的重要属性

1. **name（名称）**：Cookie 的键，用于标识该 Cookie。
2. **value（值）**：Cookie 的值，与名称配对存储数据。
3. **expires（过期时间）**：指定 Cookie 失效的具体时间。未设置时为会话 Cookie，浏览器关闭即失效。
4. **path（路径）**：指定 Cookie 有效的 URL 路径，只有该路径下的请求才会携带此 Cookie。
5. **domain（域）**：指定 Cookie 有效的域名，允许子域共享 Cookie。
6. **secure**：指定 Cookie 仅在 HTTPS 连接下发送，提升安全性。
7. **HttpOnly**：指定 Cookie 不能被 JavaScript 访问，防止 XSS 攻击。
8. **SameSite**：限制 Cookie 的跨站发送行为，增强安全性。常见值有 `Strict`、`Lax` 和 `None`。

```javascript
// 设置 Cookie
document.cookie = "username=JohnDoe; expires=Fri, 31 Dec 2025 23:59:59 GMT; path=/";

// 读取所有 Cookie
console.log(document.cookie);

// 删除 Cookie（通过设置过期时间为过去的时间）
document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT; path=/";
```
## Cookie的处理流程

1. **设置 Cookie**：服务器通过响应头或客户端通过 JavaScript 设置 Cookie。
2. **存储 Cookie**：浏览器将 Cookie 保存在本地（通常是内存或硬盘）。
3. **发送 Cookie**：浏览器每次向同一域名的服务器发送请求时，会自动携带相关 Cookie。
4. **服务器读取 Cookie**：服务器从请求头中读取 Cookie，实现会话管理等功能。
5. **更新或删除 Cookie**：服务器或客户端可以通过设置新的值或过期时间来更新或删除 Cookie。




### Web Storage 和 Cookie 的区别

| 特性            | Cookie                          | Web Storage（localStorage/sessionStorage）      |
|-----------------|---------------------------------|------------------------------------------------|
| 存储容量        | 约 4KB                          | 约 5MB（localStorage 和 sessionStorage 各自独立）|
| 与服务器通信    | 每次请求都会自动携带到服务器    | 仅在本地存储，不会自动发送到服务器              |
| 生命周期        | 可设置过期时间或为会话期        | localStorage 持久保存，sessionStorage 会话期    |
| 作用范围        | 指定域名和路径                  | 仅限同源页面                                    |
| 访问方式        | HTTP Header、JavaScript         | 仅支持 JavaScript 访问                          |
| 用途            | 会话管理、身份验证、跟踪等      | 本地数据缓存、前端状态管理                      |

**总结**：Cookie 适合需要与服务器通信的场景（如身份验证），Web Storage 更适合前端本地数据存储，容量更大且不会影响网络请求性能。


## 什么是 Session？

Session（会话）是一种在服务器端保存用户状态信息的机制。
每当用户访问网站时，服务器会为该用户创建一个唯一的 Session，并在服务器端存储与该用户相关的数据（如登录状态、购物车信息等）。
通常，服务器会通过在客户端设置一个包含 Session ID 的 Cookie，来标识和关联用户的 Session。
与 Cookie 不同，Session 数据保存在服务器上，更加安全，适合存储敏感信息。
Session 生命周期一般与用户的访问会话相关，用户关闭浏览器或 Session 过期后，Session 数据会被销毁。