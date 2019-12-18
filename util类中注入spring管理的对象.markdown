##### 最近项目在做数据表的一些补全字段的工作.当时写了一个工具类`xxxUtil`.后面由于需求变更,需要查询数据库中的数据.

 刚开始的做法是把`xxxUtil`类也交给Spring管理.遂加上注解`@Component`,之后`@Autowired`注入`xxxMapper`或`xxxResp`对象,由于静态方法中无法使用非静态变量,所以又定义了一个`static`的`xxxMapper`或`xxxResp`对象,然后使用`@PostConstruct`定义一个`init()`方法,将注入的对象赋值给静态变量.

虽然可以解决,但是自己都感觉有点别扭.因为工具类本身不应该依赖很多组件.

问了一下同组的高手,直接定义需要使用的`static`对象即可.然后提供一个`set()`方法,

创建`ResourceConfig`类,交给`spring`管理,注入需要的对象,然后提供一个`init()`方法（使用`@PostConstruct`修饰）,调用工具类的`set()`方法,完成赋值工作即可.

这样,工具类可不依赖于spring组件,并且需要用到的对象,使用`set()`方法注入值即可.

具体操作如下:

![](https://github.com/zhaowenxu/java_markdown_doc/blob/master/images/static_field.png?raw=true)

