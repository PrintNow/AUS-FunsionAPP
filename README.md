# AUS-FunsionAPP
AUS 官方网站：https://AUS.NowTime.cc

# API 开发文档
> 1. 由于我没空去写代码额，所以如果你会 `Lua` 你可以尝试参考这个 *API 文档* 写相关代码。
>
> 2. 如果你愿意分享你写的代码，欢迎 `Pulll Request` 或加入官方交流QQ群：773641216，上传你写好的相关代码

## 1. API `V2` 开发文档
 1. [检查更新 API 文档](/V2/API_UPDATE.md) 2018-12-21 发布

## 2. API `V1` 开发文档
 1. [检查更新 API 文档](/V1/API_POST.md)
 2. [获取公告 API 文档](API_UPDATE.md)

# Lua json 解析类库
> 代码在 `lib/json.lua`
 ## 使用方法
  1. 将 `json.lua` 文件复制到 `Fusion APP` 工程文件夹下，然后看下方示例代码
  ```
  json = require "json"
  
  -- table 转 json
  json.encode({ 1, 2, 3, { x = 10 } }) --Returns '[1,2,3,{"x":10}]'
  
  -- json 转 table
  json.decode('[1,2,3,{"x":10}]') -- Returns { 1, 2, 3, { x = 10 } }
  
  --详情请查看 https://github.com/rxi/json.lua#usage
  ```
