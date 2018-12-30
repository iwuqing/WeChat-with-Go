# 微信公众号接入服务器验证（Go实现）
## 1 基本流程
- 将token、timestamp、nonce三个参数进行字典序排序 
- 将三个参数字符串拼接成一个字符串进行sha1加密 
- 开发者获得加密后的字符串可与signature对比，标识该请求来源于微信

## 2 请求参数
| 参数 | 描述 |
|   -----  | ----- |
| signature | 微信加密签名，signature结合了开发者填写的token参数和请求中的timestamp参数、nonce参数。
timestamp  | 时间戳
nonce | 随机数
echostr | 随机字符串

## 3 注册页面填写
1. URL填写：http://**IP地址**:**监听端口**
2. Token填写自行设定的值

![注册完成页面](https://upload-images.jianshu.io/upload_images/14469959-533ac9aad8c07919.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 4 代码说明
- 监听于**3456**端口
- Token为**iwuqing**
