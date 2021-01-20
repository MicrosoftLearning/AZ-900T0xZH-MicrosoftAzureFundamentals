﻿---
wts:
    title: '21 - 计算复合 SLA（5 分钟）'
    module: '模块 06：介绍 Azure 成本管理和服务级别协议'
---
# 21 - 计算复合 SLA

在本演练中，我们将确定服务 SLA 正常运行时间百分比，然后计算应用程序复合 SLA 正常运行时间百分比。

我们的示例应用程序由这些 Azure 服务组成。我们不会深入探讨架构配置和注意事项，我们将仅概括介绍。

+ **应用服务**：托管应用程序。
+ **Azure AD B2C**：验证用户登录和管理配置文件。
+ **应用程序网关**：管理应用程序访问和缩放。 
+ **Azure SQL 数据库**：存储应用程序数据。 

# 任务 1：确定应用程序的 SLA 正常运行时间百分比值（5 分钟）

1. 在浏览器中，前往 [Azure 服务的 SLA 摘要](https://azure.microsoft.com/zh-cn/support/legal/sla/summary/) 页面。

2. 找到 **应用服务** SLA 正常运行时间值 **99.95％**。单击 **查看全部详情**，然后展开 **SLA 详细信息**。注意 **每月正常运行时间百分比** 和 **服务额度**。

3. 返回 SLA 网页，找到 **Azure Active Directory B2C** 服务并确定 SLA 正常运行时间值 **99.9％**。 

4. 找到 **Azure 应用程序网关** SLA 正常运行时间值 **99.95％**。 

5. Azure SQL 数据库使用没有为区域冗余部署配置的高级层。找到 **Azure SQL 数据库** SLA 正常运行时间值 **99.99％**。 

    **注意**：Azure SQL 数据库的不同配置和部署有不同的正常运行时间值。在计划部署与配置以及计算其成本时，清楚所需的正常运行时间值很重要。正常运行时间的微小变化会影响服务成本，并可能增加配置的复杂性。在 Azure SLA 摘要网页上可能值得关注的一些其他示例服务包括 **虚拟机**、**存储帐户** 和 **Cosmos DB**。

# 任务 2：计算应用程序复合 SLA 正常运行时间百分比

1. 如果构成应用程序的任一服务不可用，则用户将无法登录和使用该应用程序。因此，应用程序的总正常运行时间的构成如下：

    **应用服务正常运行时间百分比** X **Azure AD B2C 正常运行时间百分比** X **Azure 应用程序网关正常运行时间百分比** X **Azure SQL 数据库正常运行时间百分比** = **总正常运行时间百分比**

    换成百分比值如下：

    **99.95%** X **99.9%** X **99.95%** X **99.99%** = **99.79%**

    这是我们的应用程序使用当前服务和体系结构能够实现的正常运行时间百分比。

恭喜！你已确定了示例应用程序中每个服务的 SLA 正常运行时间百分比，并计算了该应用程序的复合 SLA 正常运行时间百分比。