# wxqrcode-generater
🐱‍👤Koa编写的微信小程序码生成接口

### 本地运行

需要先建好数据库~  
在index.js同级目录新建文件`config.js`，内容如下（根据自己服务器数据库进行填写）

```javascript
module.exports.database = {
  host: '',
  user: '',
  password: '',
  database: '',
  port: 1234
}
```
之后就可以运行起来了（服务器可用pm2进程管理）：
```bash
node index.js
```

### 接口 

注意：以下接口只列出后缀。

```bash
接口：/addMp
方法： POST
说明： 增加小程序信息
```
入参：

| 参数 | 必填 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| name | 是 | String | 小程序名 |
| appId | 是 | String | 小程序appId |
| secretKey | 是 | String | 小程序secretKey |
| avatar | 否 | String | 小程序头像 |

```bash
接口：/getCode
方法： POST
说明： 下载二维码接口
```
入参：

| 参数 | 必填 | 类型 | 说明 |
| ------ | ------ | ------ | ------ |
| appId | 是 | String | 小程序appId |
| path | 是 | String | 小程序路径，例如: "pages/index/index" |
| width | 是 | Number | 二维码宽度，单位为px |
| autoLineColor | 否 | Boolean | 自动线条颜色 |
| isHyaline  | 否 | Boolean | 是否透明底色 |

```bash
接口：/getMpList
方法： GET
说明： 获取小程序列表
```
