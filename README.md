## 概述
SimpleIFAA可信生物认证支持指纹、面容等生物识别解决方案，支持超15亿台Android手机、iOS手机（支持iPhone5s以上手机），为支付宝、淘宝、12306、建设银行、交通银行、浦发信用卡、苏宁金融、国信证券、上海CA、中国电信等数十家企业App提供了底层本地生物认证能力；轻量接入、接入更简单，更便捷.

1. 轻量接入：轻量接入，经过简单的接口调用开发，即可在Android/iOS设备上实现可信的生物认证能力，获得与支付宝钱包支付一致的安全快捷认证体验。
2. 设备覆盖率广：SimpleIFAA生物认证目前支持中国境内几乎所有支持指纹识别和面容识别的智能手机，总数超过15亿台，并每天持续增加中。
3. 金融级安全性：基于TEE环境预置TA方案，服务端和移动端实现双向认证，安全性远高于手机系统指纹，系统被Root依然安全可用。
4. 高隐私性：生物识别信息存储在手机终端本地，SimpleIFAA方案不会获取或存储用户生物识别信息。

  ---

  ![sifaademo](http://open.esandcloud.com/share/index.php/s/29Ggp78ZS5882fW/download)

## 插件的使用
#### 对外提供接口：
```js
/**
 * 执行IFAA认证
 * @param options(JSONObject), 包括如下字段：
 *        reasonTitle：弹出框标题
 *        fallbackTitle: 弹出框按钮标题（留空即不显示此按钮）
 * @param callback 执行结果回调，传入参数为对象result，result包括如下几个字段：
 *        code：执行状态码，0 为正藏，其他为异常
 *        msg：执行结果描述
 *        data ：执行结果
 */
simpleIFAAModule.sAuth(options, callback);
```

#### 使用方式
1. 将插件Esand-SimpleIfaaModule放入项目根目录下的nativeplugins文件夹下
2. 导入插件
3. 到商品地址购买免费套餐
4. 替换自己的appcode

## 其他信息
0. 插件地址：[https://ext.dcloud.net.cn/plugin?id=2366](https://ext.dcloud.net.cn/plugin?id=2366)
1. 完整接入文档：[https://esandinfo.yuque.com/books/share/324b13b7-7e24-40e0-a445-99d52c57e9db?#](https://esandinfo.yuque.com/books/share/324b13b7-7e24-40e0-a445-99d52c57e9db?#)
2. 服务器端协议文档：[https://market.aliyun.com/products/57000002/cmapi00038615.html](https://market.aliyun.com/products/57000002/cmapi00038615.html)
3. 后端管理控制台地址: [http://openali.esandcloud.com](http://openali.esandcloud.com)
4. 技术支持
```
微信：esand_info
qq: 3626921591
电话：18033076802
邮箱：ruide.li@esandinfo.com
```
![wechatqrcode](http://open.esandcloud.com/share/index.php/s/hzT4Gb0BN81svae/download)
hzT4Gb0BN81svae/download)
