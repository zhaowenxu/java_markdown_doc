java后台web开发,经常会使用oAuth2协议.使用`username`和`password`生成token,并在每一次的请求中携带该token.

后台调试接口经常使用postman,在postman中使用环境变量可以大大减少复制粘贴的情况.（比如本次请求的参数值,是上一个接口请求的结果）

具体使用步骤如下:

下面是模拟登录的接口:

![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/postman_test_token1.png?raw=true)

下面是另外的接口（经常出现请求参数或消息头中是上面接口返回的数据）:

![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/postman_test_token2.png?raw=true)

上面的请求可以优化为使用环境变量:

1. 在第一个接口中找到Tests,将获取到的内容设置为环境变量

![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/postman_test_token3.png?raw=true)

2. 第二个接口直接使用设置好的变量即可

   ![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/postman_test_token4.png?raw=true)

   注意事项:

   	两个接口要使用同一个环境变量,postman右上角设置

   ​	![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/postman_test_token5.png?raw=true)