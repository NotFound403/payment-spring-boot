## 前言
大部分的 **Java Web** 项目都会使用 **Spring**，尤其是 **Spring Boot**。所以笔者在开发过程中萌生一种直接构建于Spring依赖之上的支付开发包的想法。由于支付宝已经提供了SDK，所以只要将其初始化委托给 **Spring** 即可。剩下的硬骨头就是微信支付了。

## 微信支付V3的优势

笔者最开始实现微信支付的时候刚好**微信支付V3**版本的 **API**公布了。相比较于 **V2**版本：

- [x] 遵循统一的 **Restful** 的设计风格
- [x] 使用 **JSON** 作为数据交互的格式，不再使用XML
- [x] 使用基于非对称密钥的 **SHA256-RSA** 的数字签名算法，不再使用 **MD5** 或 **HMAC-SHA256**
- [x] 不再要求 **HTTPS** 客户端证书
- [x] 使用 **AES-256-GCM**，对回调中的关键信息进行加密保护

这种开发体验要远远好于之前的 **V2**，因此选择了微信支付V3。

## 目前支持的渠道

- [x] **微信支付V3** 全量支持，并支持多租户以同时满足移动应用App、公众号、小程序等支付场景
- [x] **支付宝**  集成SDK，作简单适配

## 功能
- 实现微信支付多商户
- 集成支付宝SDK、快速接入Spring Boot
- 实现微信支付V3 基础支付
- 实现微信支付V3 合单支付
- 实现微信支付V3 代金券
- 实现微信支付V3 微信支付分
- 实现微信支付V3 先享卡
- 实现微信支付V3 商家券
- 实现微信支付V3 批量转账到零钱

## Maven 中央仓库坐标
> 推荐使用最新版本
```xml
<dependency>
    <groupId>cn.felord</groupId>
    <artifactId>payment-spring-boot-starter</artifactId>
    <version>1.0.6.RELEASE</version>
</dependency>
```
## 采用技术
只依赖了 **Spring**已有的东西，做到了低依赖。

- **Spring**
- **Jackson**
- **Ali-pay-sdk**

## 开源协议

本项目采用[Apache2.0](https://www.apache.org/licenses/LICENSE-2.0)开源协议。

## **免责声明**

**<span style="color:red;">本项目涉及到资金交易开发，开发者需要经严格测试后方能用于生产环境，本项目不对使用者的行为负责。</span>**