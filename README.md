# laravel5.5.1

### 基本设置

1. 访问站点为了少一层public目录，请将nginx或appache或iis的根目录指向**public**目录。

2. 如果是linux系统。如果目录用户权限不够，也就是php，nginx用户组和当前文件的用户组不匹配。匹配才可读写(755)。这个时候请将根目录下的**storage**的权限设置为777。

```
chmod -R 777 storage
```

### 查看当前laravel版本

```
app()::VERSION;
http://xxx.xxx/version
```

### 基本概念

服务提供者：服务提供者是所有Laravel应用启动的中心，你自己的应用以及所有Laravel的核心服务都是通过服务提供者启动。

所有的服务提供者继承自`Illuminate\Support\ServiceProvider`类。继承该抽象类要求至少在服务提供者中定义一个方法：**register**。在register方法内，你唯一要做的事情就是绑事物到服务容器，不要尝试在其中注册任何时间监听器，路由或者任何其它功能。

在一个服务提供者中，可以通过$this->app变量访问容器，然后使用bind方法注册一个绑定，该方法需要两个参数，第一个参数是我们想要注册的类名或接口名称，第二个参数是返回类的实例的闭包。

singleton方法绑定一个只需要解析一次的类或接口到容器，然后接下来对容器的调用将会返回同一个实例。

你还可以使用instance方法绑定一个已存在的对象实例到容器，随后对容器的调用将总是返回给定的实例。

在 `config\app.php` 的 **providers** 中注册服务提供者。而门面是在 **aliases** 中注册。

更多：[http://laravelacademy.org/post/91.html](http://laravelacademy.org/post/91.html)

---

服务容器：Laravel服务容器是一个用于管理类依赖和执行依赖注入的强大工具。依赖注入听上去很花哨，其实质是通过构造函数或者某些情况下通过set方法将类依赖注入到类中。




