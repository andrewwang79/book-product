# 数据库

## 商家：mall_seller_seller

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|user_id|LONG|N||
|名称|name|VARCHAR(100)|N||
|法人|legal|VARCHAR(100)|N||
|审核|audit|INT|N|||
|性别|sex|INT|N|||
|联系电话|phone|VARCHAR(100)|N||
|头像|head_image|VARCHAR(100)|N||
|押金|deposit|decimal(16，2)|N||
|身份证正面|id_image_front|VARCHAR(100)|N||
|身份证背面|id_image_back|VARCHAR(100)|N||
|账户|account|VARCHAR(100)|N||
|可用余额|usable_balance|decimal(16，2)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 商家帐号：mall_seller_seller_account

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|seller_id|LONG|N||
|账户|account|VARCHAR(50)|N||
|名称|name|VARCHAR(100)|N||
|密码|password|VARCHAR(100)|N||
|联系电话|phone|VARCHAR(100)|N||
|描述|remark|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 销售点 mall_seller_sale_point

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商家|seller_id|LONG|N||
|名称|name|VARCHAR(50)|N||
|省|province|VARCHAR(100)|Y||
|市|city|VARCHAR(100)|Y||
|区/县|county|VARCHAR(100)|Y||
|街道|town|VARCHAR(100)|Y||
|详细地址|address|VARCHAR(100)|N||
|经度|longitude|decimal(16,2)|N||
|纬度|latitude|decimal(16,2)|N||
|联系电话|phone|VARCHAR(100)|N||
|图片列表|pics|VARCHAR(2048)|N||
|类型|type|VARCHAR(100)|N||
|备注|remark|VARCHAR(2048)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 菜单 mall_seller_menu

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商家|seller_id|LONG|N||
|名称|name|VARCHAR(50)|N||
|排序|seq|INT|N|||
|备注|remark|VARCHAR(2048)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 菜单商品 mall_seller_menu_item

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|菜单|menuId|LONG|N||
|商品|itemId|LONG|N||
|备注|remark|VARCHAR(2048)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 门店: mall_seller_shop

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|地址|address|VARCHAR(1000)|N||
|市|city|VARCHAR(100)|Y||
|区/县|county|VARCHAR(100)|Y||
|创建时间|createtime|DATE|N||
|经度|longitude|decimal(16,2)|N||
|纬度|latitude|decimal(16,2)|N||
|名称|name|VARCHAR(50)|N||
|联系电话|phone|VARCHAR(100)|N||
|图片列表|pics|VARCHAR(2048)|N||
|省|province|VARCHAR(100)|Y||
|备注|remark|VARCHAR(2048)|N||
|卖家ID|seller_id|LONG|Y||
|状态|status|INT|N|||
|街道|town|VARCHAR(100)|Y||
|营业时间|shop_hours|VARCHAR(100)|N||
|类型|type|VARCHAR(100)|Y||
