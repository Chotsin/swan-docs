---
title: swan.getStorage
header: develop
nav: api
sidebar: save_swan-getStorage
---



**解释**：从本地缓存中异步获取指定 key 对应的内容。

**百度APP中扫码体验：**

<img src="https://b.bdstatic.com/miniapp/assets/images/doc_demo/storage.png"  class="demo-qrcode-image" />

**方法参数**：Object object

**`object`参数说明**：

|参数名 |类型  |必填 | 默认值 |说明|
|---- | ---- | ---- | ----|----|
|key |String | 是 | -|  本地缓存中的指定的 key|
|success |Function   | 否  | -| 接口调用成功的回调函数，res = {data: key对应的内容}。|
|fail  |  Function  |  否  |-|  接口调用失败的回调函数|
|complete  |  Function   | 否  | -| 接口调用结束的回调函数（调用成功、失败都会执行）|

**success返回参数说明**：

|参数 | 类型 |说明|
|---- | ---- | ---- |
|data   | Object/String/Number/Array | key 对应的内容|

**示例**：
<a href="swanide://fragment/b030af90ec924e5ee3934fa2aeccb8e91569427287486" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>


> 建议先setStorage, 再getStorage

* 在 js 文件中
```js
swan.getStorage({
    key: 'xxx',
    success: res => {
        console.log('getStorage success', res);
    },
    fail: err => {
        console.log('getStorage err', err);
    }
});
```

#### 错误码

* Andriod

|错误码|说明|
|--|--|
|201|解析失败，请检查调起协议是否合法|
|1001|执行失败|

* iOS

|错误码|说明|
|--|--|
|202|解析失败，请检查参数是否正确      |

**Bugs&Tips**

通过swan.getStorage获取一个为设置的key对应值时， 目前会回调success函数并返回空字符串， 该问题会在后续版本修复，请关注公告及文档说明。
