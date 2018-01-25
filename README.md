# micro-match
撮合系统

表结构在create.sql中

撮合平台：
1，	实现买单向卖单或卖单向买的双向撮合。
2，	支持并发撮合。
3，	撮合规则可以自定义添加。


撮合规则管理：
内置3个撮合规则，金额范围规则（match_rule_amount）、撮合条数规则（match_rule_matchnum）、产品类别对应规则（match_rule_product）。可以自行开发其他规则如借款期限匹配规则、利率范围规则等等。
 


通过撮合规则列表页面设置规则实例id和参数。在撮合时可以指定使用哪几个规则实例。
金额范围规则（match_rule_amount）参数是最小金额min和最大金额max
例如{"min":100,"max":1000}
撮合条数规则（match_rule_matchnum）参数是最小条数min和最大条数max
例如{"min":1,"max":3}
产品类别对应规则（match_rule_product）参数是list形式pipeiList，每行参数为买单产品类别buyProduct、买单平台类别buyPlatform、卖单产品类别saleProduct、卖单平台类别salePlatform
例如
{"pipeiList":[{"buyProduct":"jingying","buyPlatform":"p2p","saleProduct":"jingying","salePlatform":"p2p"}]}

挂单管理
可以通过买单列表和卖单列表页面或接口，实现挂单。
 

撮合
在卖单列表中选中某条记录点击撮合实现向买单撮合，在买单列表中选中某条记录点击撮合实现向卖单撮合。点击撮合按钮时弹出输入框，输入规则实例id，多个用逗号分隔，不输默认使用所有的已配置规则实例进行撮合。

撮合结果管理
通过撮合结果列表页面或接口查询撮合结果。
 


用户管理
使用admin登录后（默认密码admin）可看到用户列表页面，可以添加或删除用户。
 

