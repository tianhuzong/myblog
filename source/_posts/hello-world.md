---
title: 删除授权
date: 2023-12-17 08:10:30
tags:php
---
## 删除授权
- - -
### (1)请求地址
<code>GET</code> <code><http://你的域名/api/api.php></code>

<u>使用HTTP GET调用</u>
- - -

### (2)接口描述
- 删除一个应用的授权
- - -

### (3)参数说明：
| 参数名称 |    参数说明    | 参数类型 | 必填  |                             备注 |
| :------- | :------------: | :------: | :---: | -------------------------------: |
| option   |      选项      |  string  |   Y   |                          userdel |
| product  |    产品key     |  string  |   Y   |            产品的key，在后台获取 |
| mode     |    用户类型    |  string  |   Y   | 产品可删除的类型：ip,qq,user，sb |
| ip       |  欲删除授权IP  |  string  |   Y   |                  在mode=ip时必填 |
| qq       |  欲删除授权QQ  |  string  |   Y   |                  在mode=qq时必填 |
| username | 删除授权的账号 |  string  |   Y   |                在mode=user时必填 |
| password |      密码      |  string  |   Y   |     上面账号的密码，留空则没密码 |
| sbid     |     设备码     |  string  |   Y   |                           设备码 |
- - -
### (4)返回参数
| 参数名称 | 参数说明 | 参数类型 |                               备注 |
| :------- | :------: | :------: | ---------------------------------: |
| code     |  状态码  |  string  |           添加成功返回1，失败返回0 |
| msg      |   说明   |  string  |                   失败返回失败原因 |
| sign     | 用户标志 |  string  | 用户的唯一标志，在某些操作中会用到 |

- - -
### （5）请求数据包示例
><code>删除ip用户</code>
```json{.line-numbers}
{
    "option":"userdel",
    "mode":"ip",
    "product":"thzsen27",
    "ip":"123.456.789.000"
}
```
><code>删除账号密码用户</code>
```cpp{.line-numbers}
{
    "option":"userdel",
    "mode":"user",
    "product":"thzsen27",
    "username":"tianhuzongauth",
    "password":"123456"
}
```
><code>删除绑定QQ的授权</code>
```cpp{.line-numbers}
{
    "option":"userdel"
    "mode":"qq"
    "product":"thzsen27"
    "qq":"959504938"
}
```
><code>设备授权删除</code>
```cpp{.line-numbers}
{
    "option":"userdel"
    "mode":"sb"
    "product":"thzsen27"
    "sbid":"27bf67524567wsf5"
}
```

### (6)返回数据包示例

<code>添加成功</code>

```cpp{.line-numbers}
{
    "code":"1"
    "msg":"成功"
    "sign":"123456"
}
```