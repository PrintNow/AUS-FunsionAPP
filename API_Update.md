# [API 文档]检查 APP 是否有更新

> 官网：https://AUS.NowTime.cc
>
> 使用说明：https://nowtime.cc/lua/331.html

### 1) 请求地址

>http://aus.nowtime.cc/api/query/update

### 2) 调用方式：HTTP GET

### 3) 接口描述：

* 获取 APP 最新版本

### 4) 请求参数:

#### GET参数:
|字段名称       |字段说明         |类型            |必填            |备注     |
| -------------|:--------------:|:--------------:|:--------------:| ------:|
|appid|APPID 从 https://aus.nowtime.cc/console/app_list 获取|string|Y|-|



### 5) 请求返回结果:
#### 5-1. 添加了 APP 和发布了更新返回的结果
```
{
    "code": 200,
    "msg": "查询成功",
    "version_code": 6,
    "version_name": "v1.5",
    "apk_url": "http://www.hnherun.com/gx/ydjk_v1.5.apk",
    "update_log": "6",
    "update_time": "1524323495"
}
```

#### 5-2. 未添加 AP P返回的结果
```
{
    "code": "404",
    "msg": "未查询到该 APP"
}
```

#### 5-3. 添加了 APP，但未发布更新返回的结果
```
{
    "code": "201",
    "msg": "开发者未发布新版本"
}
```


### 6) 请求返回结果参数说明:
|字段名称       |字段说明         |类型            |必有            |备注     |
| -------------|:--------------:|:--------------:|:--------------:| ------:|
|code|状态码.`200`:请求成功；`404`:软件不存在；其他...|string|Y|-|
|msg|消息|string|Y|-|
|version_code|版本号|string|N|仅发布了更新才有|
|version_name|版本名|string|N|仅发布了更新才有|
|apk_url|最新 APP 下载地址|string|N|仅发布了更新才有|
|update_log|更新日志|string|N|仅发布了更新才有|
|update_time|发布更新时间|string|N|仅发布了更新才有|
