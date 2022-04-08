# 数据库

## 包裹表  mall_logistics_package

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|物流单|logistics_order_id|LONG|Y||
|包裹状态|package_status|VARCHAR(250)|N||
|类型|type|VARCHAR(100)|N|实物，卡券|
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 包裹商品表  mall_logistics_package_item

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|包裹|package_id|LONG|N||
|订单|order_id|LONG|N||
|订单商品|order_item_sku_id|LONG|N||
|包裹单号|code|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 物流单表  mall_logistics_logistics_order  

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|物流公司|logistics_company|VARCHAR(100)|Y||
|运单号|tracking_number|VARCHAR(100)|N||
|提货码|pick_code|VARCHAR(100)|Y||
|物流信息|content|VARCHAR(100)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 卡券表  mall_logistics_card_coupon

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商品|item_id|LONG|N||
|券号|code|VARCHAR(250)|N||
|业务|biz_id|LONG|N||
|业务类型|biz_type|VARCHAR(100)|N||
|使用状态|use_status|VARCHAR(500)|Y||
|使用时间|use_time|DATE|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 消息模版表  mall_logistics_msg_template

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商品|item_id|LONG|N||
|内容|content|VARCHAR(250)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||
