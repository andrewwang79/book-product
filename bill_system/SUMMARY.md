# 持续计费系统
* 重点是资金和交易(2015-12-05)

# 需求
核心是金额在两个地方
1. 总部的账户实际金额是非实时的(持续计费)
1. 点位有断网可能

# 定义
* 账户里有金额，预扣金额（如果要多个点位同时使用，就要有多个预扣金额）
* 实际金额 = 金额 – 预扣金额

# 方案
类似预付费方式
1. 点位的计费消费：点位和总部周期同步预扣金额。如果周期内点位未同步，总部的预扣金额也等比例增加。等到下一次同步成功后，替换成点位的预扣金额。这样，通过app也能看到最近的实际金额。
1. 总部的消费：总部实时告知点位（正在使用的）有一笔交易，需要扣除账户金额，点位成功了再扣除总部的账户金额，意味着点位必须联网才可操作。如果告知下发了但没返回给总部（小概率事件），总部只能当失败处理，下回总部再和点位确认情况（基于点位的交易记录状态），如果扣了就加回来。
1. 点位的其它消费(买饮料等)：必须联网支付。

# 当前网点方案（单点操作）
在点位使用了（含点位断网），不能进行其它操作，只能在本点位操作。