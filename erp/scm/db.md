# 基础

## 商户(Merchant)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|名称|name|VARCHAR(100)|N||
|公司|company_name|VARCHAR(100)|N|||
|联系电话|phone|VARCHAR(100)|N||
|头像|head_image|VARCHAR(100)|Y||
|创建时间|createtime|DATE|N||

## 供应商(Supplier)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|供应商编码|code|VARCHAR(100)|N||
|名称|name|VARCHAR(100)|N||
|联系人名称|contact_name|VARCHAR(100)|N||
|联系人电话|contact_mobile|VARCHAR(100)|N||
|联系人地址|contact_address|VARCHAR(100)|N||
|开户银行|bank|VARCHAR(100)|y||
|银行帐号|bank_account|VARCHAR(100)|Y||
|备注|remark|VARCHAR(200)|Y||
|创建时间|createtime|DATE|N||

# 订单管理

## 销货单(SaleVoucher)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|外部订单号|external_no|VARCHAR(100)|N|商城订单号，二维火订单号|
|订单金额|total_amount|DECIMAL(16,2)|N||
|支付方式|pay_type|VARCHAR(100)|N|微信，支付宝，现金|
|支付时间|pay_time|DATE|N||
|商品数量|count|int(11)|N||
|收银员|cashier|VARCHAR(100)|Y||
|备注|remark|VARCHAR(200)|Y||
|创建时间|createtime|DATE|N||

## 销货单货品(SaleVoucherGoods)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|销货单|sale_voucher_id|LONG|N||
|货品|goods_id|LONG|N||
|货品名称|goods_name|VARCHAR(200)|Y||
|条形码|bar_code|VARCHAR(200)|Y||
|标售价|price|DECIMAL(16,2)|N||
|实际销售价|sale_price|DECIMAL(16,2)|N||
|数量|count|int(11)|N||
|总价|total_amount|DECIMAL(16,2)|N||
|创建时间|createtime|DATE|N||

## 销货退货单(SaleReturnVoucher)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|销货单|sale_voucher_id|LONG|N||
|外部订单号|external_no|VARCHAR(100)|N|商城退货订单号，二维火退货订单号|
|订单金额|total_amount|DECIMAL(16,2)|N||
|退款方式|refund_type|VARCHAR(100)|N|微信，支付宝，现金|
|退款时间|refund_time|DATE|N||
|商品数量|count|int(11)|N||
|收银员|cashier|VARCHAR(100)|Y||
|备注|remark|VARCHAR(200)|Y||
|创建时间|createtime|DATE|N||

## 销货退货单货品(SaleReturnVoucherGoods)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|销货退货单|sale_return_voucher_id|LONG|N||
|货品|goods_id|LONG|N||
|货品名称|goods_name|VARCHAR(200)|Y||
|条形码|bar_code|VARCHAR(200)|Y||
|退货价格|return_price|DECIMAL(16,2)|N||
|数量|count|int(11)|N||
|总价|total_amount|DECIMAL(16,2)|N||
|创建时间|createtime|DATE|N||

# 货品管理

## 货品(Goods)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|供应商|supplier_id|LONG|Y||
|名称|name|VARCHAR(100)|N||
|条码|barcode|VARCHAR(100)|N||
|品牌|brand|VARCHAR(100)|Y||
|单位|unit|VARCHAR(50)|N||
|规格属性|props|VARCHAR(50)|N||
|销售提成|sale_commission|DECIMAL(16,2)|N||   
|税率|tax_rate|DECIMAL(12,2)|N||
|会员价|vip_price|DECIMAL(16,2)|N||  
|批发价|wholesale_price|DECIMAL(16,2)|N||  
|零售价|retail_price|DECIMAL(16,2)|N||
|创建时间|createtime|DATE|N||

# 仓库管理

## 仓库(Warehouse)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|编码|code|VARCHAR(100)|Y|||
|名称|name|VARCHAR(100)|N||
|联系电话|phone|VARCHAR(100)|N||
|地址|address|VARCHAR(100)|N|||
|精度|longitude|DECIMAL(19,11)|N||
|纬度|latitude|DECIMAL(19,11)|N||
|创建时间|createtime|DATE|N||

## 货品批次(GoodsBatch)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|仓库|warehouse_id|LONG|N||
|货品|goods_id|LONG|N||
|批次号|batch_no|VARCHAR(100)|N|可手工输入|
|数量|count|INT|N|||
|进价|price|DECIMAL(16,2)|N||
|剩余数量|surplus_count|INT|N|||
|生产日期|produce_time|DATE|Y|||
|保质期|expire_time|DATE|Y|||
|创建时间|createtime|DATE|N||


## 入库单(WarehouseVoucher)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|单号|code|VARCHAR(50)|N|||
|仓库|warehouse_id|LONG|N||
|类型|type|VARCHAR(50)|N|采购，销货退货，调拨，其他|
|关联单号|relate_code|VARCHAR(50)|N|如销货退货单号|
|商品总价|total_price|DECIMAL(16,2)|N||
|备注|remark|VARCHAR(150)|Y||
|创建时间|createtime|DATE|N||

## 入库单货品(WarehouseVoucherGoods)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|货品|goods_id|LONG|N||
|批次|goods_batch_id|LONG|N||
|数量|count|INT|N|||
|备注|remark|VARCHAR(150)|Y||
|创建时间|createtime|DATE|N||

## 出库单(DeliveryVoucher)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|单号|code|VARCHAR(50)|N|||
|仓库|warehouse_id|LONG|N||
|类型|type|VARCHAR(50)|N|销货，损耗，调拨，其他|
|关联单号|relate_code|VARCHAR(50)|N|如销货单号|
|备注|remark|VARCHAR(150)|Y||
|创建时间|createtime|DATE|N||

## 出库单货品(DeliveryVoucherGoods)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|出库单|delivery_voucher_id|LONG|N||
|货品|goods_id|LONG|N||
|批次|goods_batch_id|LONG|N||
|数量|count|INT|N|||
|备注|remark|VARCHAR(150)|Y||
|创建时间|createtime|DATE|N||


## 库存(Stock)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|仓库|warehouse_id|LONG|N||
|货品|goods_id|LONG|N||
|入库数量|stock_count|INT|N||
|出库数量|delivey_count|INT|N||  
|可用数量|usable_count|INT|N||
|创建时间|createtime|DATE|N||

## 库存结余(StockBalance)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|仓库|warehouse_id|LONG|N||
|开始时间|start_time|DATE|N||
|结束时间|end_time|DATE|N||
|创建时间|createtime|DATE|N||

## 库存结余货品(StockBalanceGoods)

| 列名 | 字段 | 类型 | NULL | 说明 |
|:--------:|:--------:|:--------:|:--------:|:--------:|
|编号|id|LONG|N||
|商户|merchant_id|LONG|N||
|库存结余|stock_balance_id|LONG|N||
|期初数量|initial_count|DECIMAL(16,2)|N||
|期初税前单价|initial_pre_tax|DECIMAL(16,2)|N||
|期初税额单价|initial_tax|DECIMAL(16,2)|N||
|期初金额|initial_amount|DECIMAL(16,2)|N|价税合计=(税前单价+税额)*期初数量|
|入库数量|inventory_count|DECIMAL(16,2)|N||
|入库税前单价|inventory_pre_tax|DECIMAL(16,2)|N||
|入库税额单价|inventory_tax|DECIMAL(16,2)|N||
|入库金额|inventory_amount|DECIMAL(16,2)|N|价税合计=(税前单价+税额)*入库数量|
|出库数量|delivery_count|DECIMAL(16,2)|N||
|出库税前单价|delivery_pre_tax|DECIMAL(16,2)|N||
|出库税额单价|delivery_tax|DECIMAL(16,2)|N||
|出库金额|delivery_amount|DECIMAL(16,2)|N|价税合计=(税前单价+税额)*出库数量|
|结存数量|balance_count|DECIMAL(16,2)|N||
|结存金额|balance_amount|DECIMAL(16,2)|N||
|创建时间|createtime|DATE|N||

## 调拨单

## 盘点单

## 库存调整单
和成本调整单的关系是？

# 采购
## 采购单

## 采购退货单
