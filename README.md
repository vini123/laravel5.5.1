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


