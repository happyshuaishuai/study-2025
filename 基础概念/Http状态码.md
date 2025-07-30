## 常见的 HTTP 状态码

| 状态码 | 含义           | 说明                                   |
|--------|----------------|----------------------------------------|
| 200    | OK             | 请求成功                               |
| 201    | Created        | 请求成功并创建了资源                   |
| 204    | No Content     | 请求成功但无返回内容                   |
| 301    | Moved Permanently | 资源永久重定向                        |
| 302    | Found          | 资源临时重定向                         |
| 400    | Bad Request    | 请求有语法错误                         |
| 401    | Unauthorized   | 未授权，需要认证                       |
| 403    | Forbidden      | 服务器拒绝请求                         |
| 404    | Not Found      | 请求的资源不存在                       |
| 500    | Internal Server Error | 服务器内部错误                  |
| 502    | Bad Gateway    | 网关错误                               |
| 503    | Service Unavailable | 服务不可用                       |

更多状态码可参考 [MDN HTTP 响应状态码](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Status)。