## 1. 接口描述

本接口（ResizeCbsStorage）用于扩容指定的弹性云盘。

接口调用域名：<font style="color:red">cbs.api.qcloud.com</font>

使用限制：
1. 只支持扩容弹性云盘。云硬盘类型可以通过[DescribeCbsStorages（查询云硬盘信息）](https://cloud.tencent.com/doc/api/364/2519)接口查询，见输出参数中`portable`字段解释。随云主机创建的云硬盘需通过 [ResizeInstanceHour（调整实例配置（按量计费））](/doc/api/229/1344) 接口扩容

## 2. 输入参数

以下请求参数列表仅列出了接口请求参数，其它参数见[公共请求参数](https://cloud.tencent.com/document/product/240/8320)页面。

| 参数名称 | 必选  | 类型 | 描述 |
| --- | --- | --- | --- | 
| storageId | 是 | String | 云硬盘ID， 通过[DescribeCbsStorages（查询云硬盘信息）](/doc/api/364/2519)接口查询 |
| storageSize | 是 | Int | 扩容后的磁盘大小。必须大于当前值，最大值为4000，步长为10| 
 
## 3. 输出参数

| 参数名称 | 类型 | 描述 |
| ------- | ------- | ------- |
| code | Int | 公共错误码，0表示成功，其他值表示失败。详见[错误码页面](https://cloud.tencent.com/doc/api/364/%E9%94%99%E8%AF%AF%E7%A0%81) |
| message | String | 错误信息，详见[错误码页面](https://cloud.tencent.com/doc/api/364/%E9%94%99%E8%AF%AF%E7%A0%81)|

## 4. 错误码表

以下错误码表仅列出了该接口的业务逻辑错误码，更多公共错误码详见[云硬盘错误码](https://cloud.tencent.com/doc/api/364/4207)

| 错误代码 | 英文描述 | 错误描述 |
| ------- | ------- | ------- |
| 9003 | InvalidParameter | 参数错误 |
 
 
## 5. 示例

输入
<pre>
https://cbs.api.qcloud.com/v2/index.php?
<<a href="https://cloud.tencent.com/doc/api/229/6976">公共请求参数</a>>
&Action=ResizeCbsStorage
&storageId=disk-cw6a3g9w
&storageSize=100
</pre>

输出
```
{
    "code":"0",
    "message":""
}
```
 
 
 
