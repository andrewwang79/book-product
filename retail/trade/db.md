# 数据库

## 订单表 mall_trade_order

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|user_id|LONG|N||
|来源id|source_id|LONG|N|null：是商品订单。不是null，是服务订单|
|服务数据|source_data|VARCHAR(100)|N||
|总价|total|decimal(16，2)|N||
|折扣价|discount_price|decimal(16，2)|N||
|物流费用|logistics_fee|decimal(16，2)|N||
|订单状态|order_status|VARCHAR(100)|N||
|支付时间|pay_time|DATE|N||
|支付方式|pay_type|VARCHAR(100)|N||
|配送方式|delivery_type|VARCHAR(100)|N||
|发件人|sender|VARCHAR(20)|Y||
|发件人联系方式|send_phone|VARCHAR(20)|Y||
|发件地址|send_address|VARCHAR(200)|Y||
|收件人|recipient|VARCHAR(200)|Y||
|收件人联系方式|recipient_phone|VARCHAR(20)|Y||
|收件人地址|recipient_address|VARCHAR(200)|Y||
|经度|longitude|decimal(19，11)|N||
|纬度|latitude|decimal(19，11)|N||
|支付超时时间|expire_time|DATE|N||
|下次修改状态时间|next_status_time|DATE|N||
|备注|remark|VARCHAR(200)|N||
|是否隐藏|hide|bit|N|||
|线上线下|online|bit|N|||
|需要发票|need_invoice|bit|N|||
|销售渠道|channel|INT|N|||
|设备号|device_no|VARCHAR(200)|N||
|提交订单的来源|environment|VARCHAR(50)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 订单详情表 mall_trade_order_item_sku

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|用户|user_id|LONG|N||
|商品|item_id|LONG|N||
|商品Sku|item_sku_id|LONG|N||
|商品名称|item_name|VARCHAR(100)|N||
|封面图片|cover_pic|VARCHAR(100)|N||
|数量|count|INT|N|||
|单价|price|decimal(16，2)|N||
|折扣价格|discount_price|decimal(16，2)|N||
|支付金额|total|decimal(16，2)|N||
|支付时间|pay_time|DATE|N||
|过期时间|expire_time|DATE|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 订单历史表 mall_trade_order_hs

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|订单状态|order_status|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 优惠记录表 mall_trade_order_promotion

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|优惠业务|biz_id|LONG|N||
|优惠业务类型|biz_type|VARCHAR(100)|N||
|名称|name|VARCHAR(100)|N||
|优惠金额|preferential_price|decimal(16，2)|N||
|优惠结果|preferential_result|text|N|结果以json的格式存|
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 代付单表 mall_trade_behalf_pay_order  

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|请求方|request_user_id|LONG|N||
|代付方|response_user_id|LONG|Y||
|代付方手机号|response_mobile|VARCHAR(100)|N||
|金额|amount|decimal(16，2)|N||
|超时时间|expire_time|DATE|N||
|请求方支付单|request_pay_order_id|LONG|N||
|代付方支付单|response_pay_order_id|LONG|Y||
|订单状态|order_status|VARCHAR(100)|N||
|支付方式|pay_type|VARCHAR(100)|Y||
|备注|remark|VARCHAR(100)|Y||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 代付单历史表 mall_trade_behalf_pay_order_his

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|代付单|behalf_pay_order_id|LONG|N||
|订单状态|order_status|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 支付单表 mall_trade_pay_order

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|user_id|LONG|N||
|支付类型|pay_type|VARCHAR(100)|N||
|支付金额|pay_total|decimal(16，2)|N||
|手续费|counter_fee|decimal(16，2)|N||
|支付状态|pay_status|VARCHAR(100)|N||
|描述|remark|VARCHAR(100)|N||
|超时时间|expire_time|DATE|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 支付明细表 mall_trade_pay_detail

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|支付单|pay_order_id|LONG|N||
|支付类型|pay_type|VARCHAR(100)|N||
|描述|remark|VARCHAR(1024)|N||
|支付帐号|account|VARCHAR(1024)|N||
|支付金额|pay_total|decimal(16，2)|N||
|收款帐号|cheque_account|VARCHAR(1024)|N||
|收款金额|cheque_total|decimal(16，2)|N||
|手续费|counter_fee|decimal(16，2)|N||
|交易号|trade_no|VARCHAR(100)|N||
|外部交易号|out_trade_no|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 订单支付单 mall_trade_order_pay_order

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|支付单|pay_order_id|LONG|N||
|订单|order_id|LONG|N||
|类型|type|VARCHAR(100)|N||
|内部交易号|inner_trade_no|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 发票表 mall_trade_invoice

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|订单|order_id|LONG|N||
|发票抬头|customer|VARCHAR(100)|Y||
|发票内容|content|VARCHAR(50)|Y|办公用品，电脑配件，耗材等|
|类型|type|VARCHAR(50)|Y|普通发票，电子发票，增值税发票|
|单价|unit_price|decimal(16，2)|N||
|数量|quantity|INT|N|||
|开票状态|state|INT|N|||
|金额|amount|decimal(16，2)|N||
|发票代码|code|VARCHAR(100)|N||
|发票号码|invoice_no|VARCHAR(100)|N||
|开票人|drawer|VARCHAR(100)|N||
|收款人|payee|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 退货单表 mall_trade_return_order

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|用户|user_id|LONG|N||
|订单|order_id|LONG|N||
|退货单状态|return_order_status|VARCHAR(100)|N||
|退货原因|cause|VARCHAR(500)|Y||
|退款总价|total_price|decimal(16，2)|N||
|退款方式|refund_type|VARCHAR(50)|Y||
|退货收件人|recipient|VARCHAR(100)|Y||
|退货地址|recipient_address|VARCHAR(100)|Y||
|退货联系方式|recipient_phone|VARCHAR(100)|Y||
|快递单号|tracking_number|VARCHAR(100)|Y||
|快递公司|express|VARCHAR(100)|Y||
|退货照片集|pics|VARCHAR(1024)|N||
|退货支付号码|pay_amount|VARCHAR(100)|Y||
|退款标题|title|VARCHAR(100)|Y||
|下次修改状态时间|next_status_time|DATE|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||


## 退货单详情表 mall_trade_return_order_item_sku

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|退货单|return_order_id|LONG|N||
|订单项|order_item_id|LONG|N||
|商品|item_id|LONG|N||
|商品Sku|item_sku_id|LONG|N||
|数量|count|INT|N|||
|单价|price|decimal(16，2)|N||
|折扣价|discount_price|decimal(16，2)|N||
|总价|total|decimal(16，2)|N||
|首图|cover_pic|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 退货单历史表 mall_trade_behalf_pay_order_his

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|退货单|return_order_id|LONG|N||
|退货状态|return_status|VARCHAR(100)|N||
|备注|remark|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 退款单表 mall_trade_refund_order

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|相关id|relation_id|LONG|N||
|相关类型|type|VARCHAR(100)|N||
|用户|user_id|LONG|N||
|退款金额|refund_total|decimal(16，2)|N||
|备注|remark|VARCHAR(100)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||

## 退款单明细表 mall_trade_refund_order_detail

|列名|字段|类型|NULL|说明|
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|退款单|refund_order_id|LONG|N||
|退款方式|pay_type|VARCHAR(100)|N||
|备注|remark|VARCHAR(100)|N||
|支付帐号|account|VARCHAR(100)|N||
|退款金额|refund_total|decimal(16，2)|N||
|收款账户|cheque_account|VARCHAR(100)|N||
|收款金额|cheque_total|decimal(16，2)|N||
|手续费|counter_fee|decimal(16，2)|N||
|创建时间|createtime|DATE|N||
|状态|status|INT|N|||
