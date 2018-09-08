# 1、技术栈
Asp.net core Web API + Autofac + EFCore + Element-UI + SqlServer2008R2
# 2、项目结构图
简要介绍下各工程：

Account：net core Web API类型，为前端提供Rest服务

Account.Common：公共工程，与具体业务无关，目前里边仅仅有两个类，自定义业务异常类及错误码枚举类

Account.Entity：这个不要问我

Account.Repository.Contract：仓储契约，一般用于隔离服务层与具体的仓储实现。做隔离的目的是因为与仓储实现直接依赖的数据访问技术可能有很多种，隔离后我们可以随时切换

Account.Repository.EF：仓储服务的EFCore实现，从工程名字应该很容易可以看出来，它实现Account.Repository.Contract。如果这里不想用EF，那我们可以随时新建个工程Account.Repository.Dapper，增加Dapper的实现

Account.Service.Contract：服务层契约，用来隔离Account工程与具体业务服务实现

Account.Service：业务服务，实现Account.Service.Contract这个业务服务层中的契约

Account.VueFE：这个与之前一样，静态前端站点，从项目工程图标上那个互联网球球还有名字中VueFE你就应该能猜出来

　　与之前那篇文章重点在Element-UI和Vue不同，这篇文章重点在后台，在.net core。
