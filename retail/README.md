# 零售系统

## 术语
| 名称 | 定义 | 说明 |
| :----: | ---- | ---- |
| 型号 | 一个类别的产品 |  |
| 产品 |  |  |
| 货号 | 生产方自定义，基于产品和生产批次 |  |
| 条形码 | 产品代码 |  |
| UPC | 12位数字。美国统一代码委员会制定的一种商品用条码，主要用于美国和加拿大地区 |  |
| EAN | 13位数字。欧洲通用商品条形码，由前缀部分、制造厂商代码、商品代码和校验码组成 |  |
| SKU | 库存单位 |  |
| 商品 | item | 含商品规格列表 |
| 商品规格 | 关联SKU(间接关联产品)，售价 |  |
| 供应商 | 生产方，相对销售方的角色 |  |
| 分销商 | 销售方，相对生产方的角色 | 是渠道，可以押金，进货 |

# 分析
## 商品
| 项 | 分类 | 类目 | 属性 | 规格 | 商户权力 |
| :----: | ---- | ---- |
| 网点-美团 | 自定义 | 无 | 自定义 | 自定义 | 松 |
| 网点-百度 | 自定义 | 预置(3级) | 基于类目预置 | 无 | 比美团严格 |
| 网点-有赞 | 自定义 | 无 | 无 | 预置 |  |
| 商户商城-有赞 | 自定义 | 预置(1级) | 无 | 属性名类目预置 + 属性值自定义 |  |
| 商户商城-我司 | 自定义 | 自定义 | 基于类目预置 | 自定义 | 有控制权 |

## 库存
1. 有赞只有库存数，通过商家编码关联进销存
1. 美团等关联到仓库位置
1. 一个网点只关联一个仓库

## 营销
1. 预售
1. 团购

# 参考
## 零售系统
1. 系统账号

| 项 | 帐号 | 密码 | 链接 | 备注|
| :----: | ---- | ---- |----|
| 美团外卖 | wmdfxs329042 | JBmoL8716 | http://e.waimai.meituan.com/ | |
| 有赞 | 13918143204 | orange7 | https://www.youzan.com/ | |
| 点点客 | 暂无 | 暂无 | http://www.dodoca.com/ | |
| 闪电购 | 11111111220 | asd123 | http://ka.52shangou.com/kaweb/login | https://www.ele.me/shop/1055503 |
| 思讯母婴 | 1001 | 1001 | http://demo.sisseshop.com.cn:8088/EWmy/Login.aspx | |
| 二维火 | admin | ZI2PME |  | 商户号：SC3084 |

1. 链接
  1. [商米](http://www.sunmi.com/)
  1. [来客](http://www.likeit.cn/)

## 商城
1. opencart
1. ecshop

## 资料
* [非小型电子商务系统设计经验分享](http://www.cnblogs.com/mmmjiang13/archive/2012/07/05/2575538.html)
* [从淘宝数据结构来看电子商务中商品属性设计](http://www.cnblogs.com/mmmjiang13/archive/2011/04/21/1983079.html)
* [产品型号、货号、条形码有什么不同](http://wenku.baidu.com/link?url=53Zzt-yWY9AN-f1iHdIFBm8ck8ibEHWDFlHOzv3gfKMSEjaQ1QZ1f3j7PSWzDxaGMtE3sRaarb3xucvWWDGAvVSOW9d7lw6FVRJJ-68pwS_)
* 商品和SKU
  * [淘宝的产品](http://open.taobao.com/docs/api.htm?apiId=4)
  * [有赞的网店商品](https://www.youzanyun.com/apilist/detail/group_item/item/youzan.item.create)
  * [有赞的网店商品SKU](https://www.youzanyun.com/apilist/detail/group_item/item/youzan.item.sku.update)
  * [有赞的网点商品](https://www.youzanyun.com/apilist/detail/group_shop/multi_store/youzan.multistore.goods.sku.get)
* 分销
  [魔筷](http://bbs.mockuai.com/portal.php?mod=view&aid=32)
  [有赞的销售员](https://help.youzan.com/qa#/menu/2194/detail/772)
* [有赞的API](https://www.youzanyun.com/apilist)
* [有赞的多网点方案](https://www.youzan.com/intro/solution/dmd)
* [订单编码规则](https://www.zhihu.com/question/19805896)
* [实例分享：B2C自营电商APP的优惠券设计方案1.0](http://www.woshipm.com/pd/570563.html)
* 淘宝大学
  * [新手如何开淘宝店](https://daxue.taobao.com/markets/daxue/xinshou)
  * [新手卖家物流选择 后台相关设置](http://v.xue.taobao.com/learn.htm?courseId=61587)
  * [新手卖家如何进行快速发货](http://v.xue.taobao.com/learn.htm?courseId=61676)
  * [新手卖家退换货订单管理和加单，退单，改单](http://v.xue.taobao.com/learn.htm?courseId=61661)

## 淘宝交易相关状态
### 订单状态
```
TRADE_NO_CREATE_PAY(没有创建支付宝交易)
WAIT_BUYER_PAY(等待买家付款)
SELLER_CONSIGNED_PART(卖家部分发货)
WAIT_SELLER_SEND_GOODS(等待卖家发货,即:买家已付款)
WAIT_BUYER_CONFIRM_GOODS(等待买家确认收货,即:卖家已发货)
TRADE_BUYER_SIGNED(买家已签收,货到付款专用)
TRADE_FINISHED(交易成功)
TRADE_CLOSED(付款以后用户退款成功，交易自动关闭)
TRADE_CLOSED_BY_TAOBAO(付款以前，卖家或买家主动关闭交易)
PAY_PENDING(国际信用卡支付付款确认中)
WAIT_PRE_AUTH_CONFIRM(0元购合约中)
```
### 退款状态
```
WAIT_SELLER_AGREE(买家已经申请退款，等待卖家同意)
WAIT_BUYER_RETURN_GOODS(卖家已经同意退款，等待买家退货)
WAIT_SELLER_CONFIRM_GOODS(买家已经退货，等待卖家确认收货)
SELLER_REFUSE_BUYER(卖家拒绝退款)
CLOSED(退款关闭)
SUCCESS(退款成功)
```
### 物流状态
```
CREATED(订单已创建)
RECREATED(订单重新创建)
CANCELLED(订单已取消)
CLOSED(订单关闭)
SENDING(等候发送给物流公司)
ACCEPTING(已发送给物流公司,等待接单)
ACCEPTED(物流公司已接单)
REJECTED(物流公司不接单)
PICK_UP(物流公司揽收成功)
PICK_UP_FAILED(物流公司揽收失败)
LOST(物流公司丢单)
REJECTED_BY_RECEIVER(对方拒签)
ACCEPTED_BY_RECEIVER(发货方式在线下单：对方已签收；自己联系：卖家已发货)
```
