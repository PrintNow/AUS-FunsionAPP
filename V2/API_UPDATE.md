

## 检查更新接口(V2)

### 1) 请求地址

> https://aus.nowtime.cc/api/v2/update

---

>> #### 1-1) 请求示例：
>> https://aus.nowtime.cc/api/v2/update?appid=10001&packageName=cn.nowtool.test

### 2) 调用方式：HTTP GET

### 3) 接口描述：

* 获取 APP 最新版本信息 (https://aus.nowtime.cc)

### 4) 请求参数:

#### `GET` 参数:
|字段名称       |字段说明         |类型            |必填            |备注     |
| -------------|:--------------:|:--------------:|:--------------:| ------:|
|appid|在 <a href="https://aus.NowTime.cc" target="_BLANK">aus.NowTime.cc</a> 添加 APP 对应的 APPID|string|Y|-|
|packageName|应用软件包名，例如（cc.nowtime.aus）|string|Y|必须传入，但不进行校验。以后需要校验包名，但以后会启用包名校验，如果包名与APPID不符合，则返回错误|



### 5) 请求返回结果:

```
{
    "code": 10000,
    "reason": "success",
    "version_code": 3,
    "version_name": "1.2",
    "apk_url": "https://vip.d0.baidupan.com/file/?UDZaZFxtAjNRWAI6U2ZWOldoADgAPgf1ViFUfwUrB2MBbVdlDTEEIwAzAXkLPgFwUWACIV9mAWpVPlAzVlUBaVA0WjBcNwJnUTQCZlMwVm9XNQAjADkHdlZsVGMFbAc0AThXNQ1lBGUAcAEnCy8BPVE5AjdfMQE7VX1QZ1Y4AS9QYVo7XC4CNFFkAmxTYlZjVz0AYABvBzJWZFQ3BW8HZAE2V2INYgQyADABYAtrATRRbwIyX2EBMVVqUG5WbAEwUGhaNFxjAnhRZgIkU2xWcVd4AHYAOgd3VjhUNgVkBzcBM1c5DWgEaABkAXELKwFpUWYCYl9mAT5VY1BjVj4BNVBhWjRcMwJjUTUCZFMp",
    "update_strategy": 1,
    "update_trigger": "all",
    "update_log": "<font color=\"#FF0000\">解决</font>提出问题的人",
    "update_time": "2018-12-17 19:19:51"
}
```


### 6) 请求返回结果参数说明:
|字段名称       |字段说明         |类型            |必有            |备注     |
| -------------|:--------------:|:--------------:|:--------------:| ------:|
|code|状态码|string|Y|请查看下方的 `6-1)` code 字段返回解析|
|reason|原因|string|Y||
|version_code|版本号(version Code)|int|Y|-|
|version_name|版本名(Version Name)|string|Y|-|
|apk_url|新版本 APP 下载地址|string|Y|如果用户发布更新时填写的是蓝奏云分享链接，则自动解析成直链接|
|update_strategy|是否强制更新|int|Y|`1`：不强制更新；`2`：强制更新|
|update_trigger|更新提示网络环境（以 `#` 分割）|string|Y|更新提示网络环境。<br/>`all`：所有网络；`wifi`：Wi-Fi网络下；<br/>`4g`：4G网络下；`3g`：3G网络下；<br/>`2g`：2G网络下；`other`：其他网络环境下|
|update_log|更新日志|string|Y|-|
|update_time|发布更新时间|string|Y|-|


> #### 6-1) `code` 字段返回解析
|状态码       |状态码解释         |
| -------------|:--------------:
|10000|正常|
|10001|未传入 `appid` 或者 `packageName` 参数，详情看返回的 `reason` 字段|
|10002|未查询到该 APP，请检查 `appid` 是否填入正确，详情看返回的 `reason` 字段|
|10003|包名与根据 `appid` 查询到的包名不符合，请检查 `appid` 或者 `packageName` 是否填入正确，详情看返回的 `reason` 字段|
|10004|开发者未在控制台发布新版本，请开发者发布一个版本更新|





