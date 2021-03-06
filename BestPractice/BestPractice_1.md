# 查询结果如何突破最大 1000 条的限制？

#### 问题详情
查询结果默认最多只能返回 1000 条数据，当我需要的数据量超过了 1000，该怎么办？

#### 解决方案
可以通过每次变更查询条件，来继续从上一次的断点获取新的结果，譬如：

第一次查询，createdAt 时间在 `2015-12-01 00:00:00` 之后的 1000 条数据（最后一条的 createdAt 值是 x）；

第二次查询，createdAt 在 x 之后的 1000 条数据（最后一条的 createdAt 是 y）；

第三次查询，createdAt 在 y 之后的 1000 条数据（最后一条是 z）；

......

以此类推。
