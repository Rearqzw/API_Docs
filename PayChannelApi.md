# 支付渠道下单API文档

* [返回文档首页](https://github.com/coinWinApi/API_Docs)

目前开放了B端商户下单api，我们将提供B端商户accessKey与secretKey,accessKey用来授权，secretKey用来签名，切勿暴露accessKey与secretKey，具体接口与回调流程请阅读以下文本。
# 接口说明
- 签名说明：这里的签名采用sha256进行签名。对业务报文体的JSON对象的字符串签名。
- 签名key：secretKey 【secretKey由接口方提供】
- 签名对象：注有签名要求的键值对
- 例如：请求 https://xxx.com:xxxx/MapSystem/paychannel/createtrade参数有totalamount、paytype、outtradeno，则需要对 http://xxx.com:xxxx/MapSystem/paychannel/createtrade?accessKey=****&outtradeno=xxxxxxxxxx&paytype=1&timestamp=1567412503000&totalamount=100 进行sha256加密（注意参数的排序是按照键进行升序排序的,所有参与签名的参数,参数名一律为小写）然后在请求头里带上sign参数，值就是得到的密文



#### 接口列表 (注：Data为业务报文体，json对象，该对象的key切记务必要小写，不然无法验签通过)

|接口地址|请求方式|接口说明|
| --------   | -----  | ----  |
|MapSystem/paychannel/createtrade|post|B端商户下单接口|

### 请求参数

|参数名称|是否必须|类型|描述|默认值|取值范围|是否加入签名|
| --------   | -----  | ----  | ----  | ----  | ----  | ----  |
|AccessKey|true|string|授权key|无|接口方提供|true|
|TimeStamp|true|string|（当前时间）毫秒级精度|无|时间戳，例：1567412503000|true|
|Signature|true|string|签名数据|无|||
|Data|true|json|业务报文体|无|||
| --------   | -----  | ----  | ----  | ----  | ----  | ----  |
|Data业务报文体参数名称|是否必须|类型|描述|默认值|取值范围|
|Data.totalamount|true|double|下单金额|无|暂时仅提供(100,200,299,499,999,1497,1998,2997,4995)|true|
|Data.paytype|true|int|支付方式|无|1-支付宝，2-微信|true|
|Data.outtradeno|false|string|下游订单Id |无|无|true|

### 返回参数

|参数名称|是否必须|类型|描述|默认值|取值范围|
| --------   | -----  | ----  | ----  | ----  | ----  |
|code|true|int|业务码||200：成功、1001：失败|
|success|true|bool|操作是否成功|true：成功 false：失败|true、false|
|message|true|string|文本信息|||
|data|true|json|结果业务体||||
