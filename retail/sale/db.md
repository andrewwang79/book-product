# 数据库

## 商品 mall_sale_item  

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|卖家|seller_id|LONG|N||
|产品|product_id|LONG|N||
|名称|name|VARCHAR(250)|N||
|副名称|sub_name|VARCHAR(250)|N||
|类型|type|INT|N| 1：普通商品  11：分销商品 21：虚拟商品 21：电子卡券 |
|市场价|price|decimal(16,2)|Y||
|最低价|low_price|decimal(16,2)|Y||
|销售价|discount_price|decimal(16,2)|Y||
|库存|stock|INT(11)|N||
|已销售数量|sold_count|INT(11)|N||
|封面图片|cover_pic|VARCHAR(1024)|N||
|图片列表|pics|VARCHAR(500)|N||
|描述|remark|VARCHAR(1024)|Y||
|属性列表|props|VARCHAR(1024)|Y||
|商品参数|parameter|VARCHAR(4096)|Y||
|上架时间|start_sale_time|DATE|Y| 商品定时上架（定时开售）的时间(auto_listing_time) |
|下架时间|end_sale_time|DATE|Y| 商品定时下架（定时结束）的时间 |
|上架or下架|shelves|INT(2)|N||
|是否上架过|shelved|bit|N||
|支持开发票|provide_invoice|bit|N||
|售后服务|sale_support|VARCHAR(1024)|N||
|提成比例|scale|decimal(16,2)|N||
|序列商品|is_sn|bit(1)|Y||
|外部编号|outer_id|VARCHAR(100)|Y| 商家为商品设置的外部编号，可与商家外部系统对接 |
|发货类型|etd_type|INT(2)|N| 1, 固定时间开始发货, 2, 付款n天后发货。默认是2 |
|预计发货时间|etd_time|DATE|Y||
|付款成功后发货天数|etd_days|INT|N| 默认0 |
|运费类型|delivery_type|INT(2)|N| 1：统一运费；2：运费模版。默认是1 |
|运费|delivery_fee|decimal(16,2)|N|默认5元|
|运费模板号|delivery_template_id|LONG|Y|  |
|运费模板参数|delivery_template_fee|TEXT|Y| json格式 |
|二维码|qr_code|VARCHAR(100)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 商品Sku mall_sale_item_sku  

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商品|item_id|LONG|N||
|商家|seller_id|LONG|N||
|名称|name|VARCHAR(250)|N||
|市场价|price|decimal(16,2)|Y||
|折扣价|discount_price|decimal(16,2)|Y||
|已销售数量|sold_count|INT(11)|N||
|库存|stock|INT(11)|N||
|总数量|total|INT(11)|N||
|封面图片|cover_pic|VARCHAR(1024)|N||
|图片列表|pics|VARCHAR(500)|N||
|属性列表|props|VARCHAR(1024)|Y||
|商品参数|parameter|VARCHAR(4096)|Y||
|二维码|qr_code|VARCHAR(100)|Y||
|商家编码|seller_code|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 购物车 mall_sale_cart

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|user_id|LONG|N||
|备注|remark|VARCHAR(500)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 购物车项 mall_sale_cart_item_sku

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|购物车|cart_id|LONG|N||
|商家|seller_id|LONG|N||
|店铺名称|shopName|VARCHAR(100)|N||
|商品|item_id|LONG|N||
|商品SKU|item_sku_id|LONG|N||
|商品名称|itemName|VARCHAR(100)|N||
|营销业务|biz_id|LONG|N||
|营销业务类型|biz_type|VARCHAR(50)|N||
|数量|count|INT(11)|N||
|存的时候市场价|price|decimal(16,2)|N||
|存的时候销售价|discount_price|decimal(16,2)|N||
|选中|selected|bit(1)|Y||
|备注|remark|VARCHAR(500)|Y||
|更新时间|update_time|DATE|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 历史搜索 mall_sale_user_search_hs

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|userId|LONG|N||
|名称|name|VARCHAR(100)|N||
|备注|remark|VARCHAR(2048)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 热搜标签 mall_sale_hot_search_tag

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|名称|name|VARCHAR(100)|N||
|次数|count|INT|N||
|备注|remark|VARCHAR(2048)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 类目: mall_sale_category  

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|保证金|deposit|LONG|N||
|是否虚拟|is_virtual|INT|N||
|名称|name|VARCHAR(250)|N||
|上级类目|parent_id|LONG|Y||
|图片列表|pics|VARCHAR(1024)|N||
|备注|remark|VARCHAR(2048)|N||
|排序|seq|INT|N||
|提成比例|scale|VARCHAR(1024)|Y||
|类型|type|VARCHAR(1024)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 产品: mall_sale_product

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|品牌|brand_id|LONG|N||
|名称|name|VARCHAR(100)|N||
|排序|seq|INT|N||
|备注|remark|VARCHAR(2048)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 关联属性表: mall_sale_prop_relation

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|属性名编号|prop_name_id|LONG|Y||
|属性值编号|prop_value_id|LONG|Y||
|关联类型|biz_type|VARCHAR(50)|Y||
|类型|type|VARCHAR(50)|Y||
|内容|content|VARCHAR(1024)|Y||
|关联编号|biz_id|LONG|Y||
|创建时间|createtime|DATE|Y||
|状态|status|INT|N|||

## 属性值: mall_sale_prop_value

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|属性名编号|prop_name_id|LONG|Y||
|名称|name|VARCHAR(100)|N||
|备注|remark|VARCHAR(2048)|N||
|排序|seq|INT|N||
|类型|type|VARCHAR(50)|Y||
|产品id|product_id|LONG|N||
|创建时间|createtime|DATE|Y||
|状态|status|INT|N|||

## 销售点: mall_sale_sale_point

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|地址|address|VARCHAR(1000)|N||
|市|city|VARCHAR(100)|Y||
|区/县|county|VARCHAR(100)|Y||
|经度|longitude|decimal(16,2)|N||
|纬度|latitude|decimal(16,2)|N||
|名称|name|VARCHAR(50)|N||
|联系电话|phone|VARCHAR(100)|N||
|图片列表|pics|VARCHAR(2048)|N||
|省|province|VARCHAR(100)|Y||
|备注|remark|VARCHAR(2048)|N||
|卖家ID|seller_id|LONG|Y||
|街道|town|VARCHAR(100)|Y||
|类型|type|VARCHAR(100)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||
