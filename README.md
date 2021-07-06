# Thrift.learning
## Thrift IDL 文件
```
namespace jave com.test.thrift.demo

struct News {
  1: i32 id;
  2: string name;
  3: string content;
  4: string mediaFrom;
  5: string author;
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
  1: string name;
  2: i32 age;
  3: string gender;
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
  1: i32 code;
  2: string reason;
}
```
