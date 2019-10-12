## 简单记：在cygwin安装jekyll

```
apt-cyg install ruby
apt-cyg ruby-devel
apt-cyg gcc-g++
apt-cyg make
```

然后执行：

```
gem install jekyll
```

过程中会编译ruby的插件，需要用到GCC和G++。