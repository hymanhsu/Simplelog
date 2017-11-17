## simple_log是一个轻量的c++版本日志组件
## 特点

  * 简洁但是功能实用
  * 线程安全


## 配置文件
 * 如果没有找到,会将日志以debug级别输出到控制台
```
 log_level=INFO
 log_dir=log
 log_file=simple.log
 retain_day=7
```


## 编译&安装
```
mkdir build
cd build
cmake ..
make
sudo make install
```

## 例子:
```c++

#include "simple_log.h"

int main() {
    int ret = log_init("simple_log.conf");
    if (ret != 0) {
    	printf("log_init error!\n");
        return 1;
    }
    LOG_INFO("%s", "this is a info log");
    return 0;
}
```

## 输出
```
 2014-10-25 15:43:29.216 INFO test/simple_log_test.cpp(5): this is a info log
```
