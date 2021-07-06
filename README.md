# Thrift.learning
## Thrift IDL 文件
```
namespace jave com.test.thrift.demo

struct News {
  1: i32 id,
  2: string name,
  3: string content,
  4: string mediaFrom,
  5: string author
}

service IndexNewsOperatorServices {
  bool indexNews(1: NewsModel indexNews),
  bool removeNewsById(1: i32 id)
}
```
### 结构体（struct）
* 就像C语言一样，Thrift支持struct类型，目的就是将一些数据聚合在一起，方便传输管理。struct的定义形式如下：
```
struct People {
  1: string name,
  2: i32 age,
  3: string gender
}
```
### 枚举（enum）
* 枚举的定义类型和Jave的Enum定义类似：
```
enum Gender {
  MALE,
  FEMALE
}
```
### 异常（exception）
* Thrift支持自定义exception，规则与struct一样
```
execption RequestException {
  1: i32 code,
  2: string reason
}
```
### 服务（service）
* Thrift定义服务相当与Jave中创建Interface一样，创建的service经过代码生成命令之后就会生成客户端和服务端的框架代码。定义形式如下：
```
service HelloWorldService {
  string doAction(1: string name, 2: i32 age)
}
```
### 类型定义
* Thrift支持类似C++一样的typedef定义：
```
typedef i32 int
typedef i64 long
```
### 常量（const）
* Thrift也支持常量定义，使用const关键字：
```
const i32 MAX_RETRIES_TIME = 10
const string MY_WEBSITE = "http://facebook.com"
```
### 命名控件
* Thrift的命名空间相当于jave中的package的意思，主要目的是组织代码。Thrift使用关键字namespace定义命名空间：
```
namespace jave com.test.thrift.demo
```
* 格式是：namespace 语言名 路径
### 文件包含
* Thrift也支持文件包含，相当与C/C++中的include，Jave中的import。使用关键字include定义：
```
include "global.thrift"
```
### 注释
* Thrift注释方式支持shell风格的注释，支持C/C++风格的注释，即#和//开头的语句都当作注释，/**/包裹的语句也是注释。
### 可选与必选
* Thrift提供两个关键字required，optional，分别用于表示对应的字段是必填的还是可选的
```
struct People {
  1: required string name,
  2: optional i32 age
}
```
