## 说明

这套识别程序的数据库是免费IP数据库、IP离线地址库。支持将IP转化为结构化的国家、省、市、县、运营商、地区信息)

0，该数据库识别是离线的。

1，该数据库基于纯真IP库，IP地址纠错相关和最新地址获取请直接去纯真官网，下面有给出地址。

2，纯真IP识别算法来源网络。

3，结构化程序来自我2012年的脑洞。


纯真IP已从03年开始存在多年且一直免费，实属不易。因为数据存储时，并不是结构化的，因此有误差在所难免。这个结构化程序，国内 ip 可以识别出省份，基本可以识别出市。运营商、县数据看运气。


## 使用说明

修改自`https://github.com/itbdw/ip-database`兼容PHP8+

```
composer require hulang/php-ip
```


```php

//根据实际情况，基本上用框架（如 Laravel）的话不需要手动引入
//require 'vendor/autoload.php';

use Ip\IpLocation;

//0配置使用
echo json_encode(IpLocation::getLocation($ip), JSON_UNESCAPED_UNICODE) . "\n";

//支持自定义文件路径
$qqwry_filepath = '/abspath/qqwry.dat';
$ipv6wry_path = '/abspath/ipv6wry.db';
echo json_encode(IpLocation::getLocation($ip, $qqwry_filepath), JSON_UNESCAPED_UNICODE) . "\n";


```

## 响应

获取成功
```json
{
  "ip": "163.177.65.160",
  "country": "中国",
  "province": "广东",
  "city": "深圳市",
  "county": "",
  "isp": "联通",
  "area": "中国广东省深圳市腾讯计算机系统联通节点"
}
```

异常
```json
{
  "error": "ip invalid"
}
```


## 感谢
1，纯真IP库

https://www.cz88.net/help?id=free


