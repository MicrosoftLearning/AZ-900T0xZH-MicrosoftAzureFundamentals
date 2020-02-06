﻿---
wts:
    title: '13 - 实现 Azure Key Vault'
    module: '模块 03 - 安全性、隐私、合规性和信任'
---
# 13 - 实现 Azure Key Vault

在本演练中，我们将创建一个 Azure Key Vault，然后在该 Key Vault 中创建一个密码机密，从而提供安全存储且集中管理的密码，以用于应用程序。

预计用时：10 分钟

# 任务 1：创建 Azure Key Vault

1. 登录至 [Azure 门户](https://portal.azure.com)。

2. 搜索并选择 **密钥保管库**，然后选择 **添加**。

3. 配置密钥保管库。查看其他选项卡，但保留默认值。 

    | 设置 | 数值 | 
    | --- | --- |
    | 订阅 | **使用你的订阅** |
    | 资源组 | **myRGKV** （新建） |
    | 密钥保管库名称 | **keyvaulttestxxx** （必须是唯一的） |
    | 地点 | **美国东部** |
    | 定价层 | **标准** |
    | | |

4. 单击 **审阅+创建**，然后单击 **创建**。 

5. 新密钥保管库部署后，单击 **前往资源**。或者，你可以通过搜索找到新的密钥保管库。 

6. 单击密钥保管库 **概述** 选项卡并记下 **DNS 名称**。通过 REST API 使用密钥保管库的应用程序将需要此 URI。

7. 花一点时间浏览一些其他的密钥保管库选项。在 **设置** 下，查看 **密钥**、**机密**、**证书**、**访问策略**、**防火墙和虚拟网络**。

    **注意**：你的 Azure 帐户是可在此新保管库上执行操作的唯一授权帐户。你可以根据需要在 **设置** 中的 **访问策略** 部分修改此设置。

# 任务 2：向 Key Vault 添加机密
        
在此任务中，我们将向密钥保管库添加密码。 

1. 在 **设置** 下，选择 **机密**，然后选择 **+生成/导入**。

2. 配置机密。将其他值保留为默认值。注意，你可以设置激活和到期日期。注意，你还可以禁用机密。

    | 设置 | 数值 | 
    | --- | --- |
    | 上传选项 | **手动** |
    | 名称 | **ExamplePasswordn** |
    | 值 | **hVFkk96** |
    | | |

3. 单击 **创建**。

4. 成功创建机密后，单击 **ExamplePassword**，请注意其状态为 **已启用**

5. 单击当前版本，注意 **机密标识符**。这是你现在可以与应用程序一起使用的 URL 值。它提供了集中管理且安全存储的密码。

6. 单击按钮 **显示机密值**，显示你先前指定的密码。

恭喜！你已创建 Azure Key Vault，然后在该密钥保管库中创建了密码机密，从而提供了安全存储且集中管理的密码，以用于应用程序。

**注意**：为避免产生额外费用，你可以删除此资源组。搜索资源组，单击你的资源组，然后单击 **删除资源组**。验证资源组的名称，然后单击 **删除**。关注 **通知**，了解删除操作的进度。