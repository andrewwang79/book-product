# 数据库

## 活动：mall_marketing_activity

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|标题|title|VARCHAR(100)|N||
|开始时间|start_time|DATE|N||
|结束时间|end_time|DATE|N||
|类型|type|VARCHAR(100)|N||
|编号|code|VARCHAR(100)|Y||
|自动生效|is_auto|INT|N||
|上线|online|VARCHAR(100)|Y||
|用户参加次数|summary_user|INT|N||
|每单购买个数|summary_order|INT|N||
|每人活动购买最大数量|summary_activity|INT|N||
|限定规则|limit_rule|VARCHAR(100)|Y||
|结果规则|result_rule|VARCHAR(100)|Y||
|备注|remark|VARCHAR(100)|Y||
|审核状态|audit|INT|N||
|商家|seller_id|LONG|Y||
|父活动|parent_id|LONG|Y||
|优先级|priority|INT|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N||

## 活动商品：mall_marketing_activity_item

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|活动|activity_id|LONG|N||
|商品|item_id|LONG|N||
|商品项|item_sku_id|LONG|N||
|市场价|price|DECIMAL(16,2)|N||
|折扣价|discount_price|DECIMAL(16,2)|N||
|数量|count|INT|N||
|销售数量|sold_count|INT|N||
|排序|seq|INT|N||
|类型|type|VARCHAR(100)|N||
|限定规则|limit_rule|VARCHAR(100)|N||
|范围|scope|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N||

## 优惠券：mall_marketing_coupon

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|名称|name|VARCHAR(100)|N||
|来源类型|source_type|VARCHAR(100)|N|平台，商家|
|销售渠道|channel|INT|N|网店销售：2|
|券编码|code|VARCHAR(100)|N||
|类型|type|VARCHAR(100)|N|代金券,折扣券,换购券|
|数量|count|INT|N||
|已领取数量|receive_count|INT|N||
|已使用数量|used_count|INT|N||
|领券开始时间|receive_start_time|DATE|N||
|领券结束时间|receive_end_time|DATE|N||
|券开始使用时间|use_start_time|DATE|N||
|券结束使用时间|use_end_time|DATE|N||
|使用门槛|threshold|decimal(16，2)|N||
|适用类型|biz_type|VARCHAR(100)|N||
|面值|value|decimal(16，2)|N||
|是否提醒|remind|bit|N||
|提醒时间|remind_time|DATE|N||
|发布时间|remind_time|DATE|N|预设字段，目前没用到|
|平台比例|sys_scale|decimal(16，2)|N||
|商家比例|seller_scale|decimal(16，2)|N||
|是否可重复使用|repeated_use|bit|N||
|是否可叠加使用|overlay_use|bit|N||
|限定规则|limit_rule|text|Y||
|备注|remark|text|Y||
|排序|seq|INT|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 活动优惠券：mall_marketing_activity_coupon

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|活动|activity_id|LONG|N||
|优惠券|coupon_id|LONG|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 点位优惠劵：mall_marketing_coupon_point

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|销售点位|point_id|LONG|N||
|优惠券|coupon_id|LONG|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 用户优惠券：mall_marketing_user_coupon

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|user_id|LONG|N||
|名称|name|VARCHAR(100)|N||
|优惠券|coupon_id|LONG|N||
|优惠券码|coupon_code|VARCHAR(100)|N||
|面值|value|decimal(16，2)|N||
|二维码|qr_code_image|VARCHAR(100)|N||
|二维码编码|qr_code|VARCHAR(100)|N||
|来源类型|source_type|VARCHAR(100)|N||
|使用状态|use_status|VARCHAR(100)|N||
|业务id|biz_id|LONG|N||
|业务类型|use_status|VARCHAR(100)|N|order,servant|
|使用时间|use_time|DATE|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 优惠券适用范围：mall_marketing_coupon_range

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|优惠券|coupon_id|LONG|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N||
|业务id|biz_id|LONG|N||
|业务类型|biz_type|VARCHAR(100)|N||

## 行为奖励：mall_marketing_action_bonus

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|行为编码|code|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|名称|name|VARCHAR(100)|N||
|备注|remark|VARCHAR(1024)|Y||
|开始时间|start_time|DATE|N||
|结束时间|end_time|DATE|N||
|状态|status|INT|N||

## 行为奖励详情：mall_marketing_action_bonus_item

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|行为编号|action_bonus_id|LONG|N||
|创建时间|createtime|DATE|N||
|数量|count|INT|N||
|类型|type|VARCHAR(100)|N||
|状态|status|INT|N||

## 优惠券码: mall_marketing_coupon_code

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|行为编码|code|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|优惠券id|coupon_id|LONG|N||
|号码|num_detail|VARCHAR(100)|Y||
|号段|num_section|VARCHAR(100)|Y||
|类型|type|VARCHAR(100)|N||
|状态|status|INT|N||
|面值|value|decimal(16，2)|N||

## 行为奖励记录: mall_marketing_user_action_bonus

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|行为编号|action_bonus_item__id|LONG|N||
|创建时间|createtime|DATE|N||
|用户|user_id|LONG|N||
|状态|status|INT|N||
