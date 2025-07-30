
1. 使用 CSS Hack 区分 IE6：
    ```css
    * html .selector { color: red; } /* 仅IE6生效 */

    部分前缀法：
        /* IE6及以下 */
        _property: value;
        /* IE7及以下 */
        *property: value;
        /* IE8及以下 */
        .property: value;
        /* 示例 */
        * html .selector { background: blue; } /* 仅IE6 */
        *+html .selector { background: green; } /* 仅IE7 */
        .selector { background: yellow\9; } /* IE8及以下 */
    ```

2. 条件注释加载专用样式：
    ```html
    <!--[if IE 6]>
    <link rel="stylesheet" type="text/css" href="ie6.css" />
    <![endif]-->
    ```

3. 避免使用 IE6 不支持的属性：
    ```css
    /* 不使用 :hover 选择器在非 a 标签上 */
    ```

4. 重置样式：
    ```css
    * { margin: 0; padding: 0; }
    ```

5. 修复 PNG 透明问题：
    ```html
    <script src="DD_belatedPNG.js"></script>
    <script>DD_belatedPNG.fix('.png-bg');</script>
    ```

6. 使用 JavaScript 修复兼容性：
    ```javascript
    if (navigator.userAgent.indexOf('MSIE 6.0') !== -1) {
      // IE6专用修复代码
    }
    ```

7. 定期测试页面显示效果：
    ```
    使用虚拟机或IE6浏览器测试页面
    ```