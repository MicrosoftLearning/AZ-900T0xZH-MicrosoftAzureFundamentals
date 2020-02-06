﻿---
wts:
    title: '07 - 实现 Azure Functions'
    module: '模块 02 - 核心 Azure 服务'
---
# 07 - 实现 Azure Functions

在本演练中，我们将创建一个函数应用，用于在出现 HTTP 请求时显示 Hello 消息。 

预计用时：30 分钟

# 任务 1：创建一个函数应用

在此任务中，我们将创建一个函数应用。

1. 登录至 [Azure 门户](https://portal.azure.com)。

2. 搜索 **函数应用**，然后单击 **+ 添加**。

3. 填写 Azure 函数应用设置字段。如果未指定，请使用默认值。 

    | 设置 | 值 |
    | -- | --|
    | 应用名称 | **function-xxx** （这必须是唯一的） |
    | 订阅 | **选择你的订阅** |
    | 资源组 | **myRGFunction** （新建） |
    | OS | **Windows** |
    | 托管计划 | **使用计划** |
    | 地点 | **美国东部** |
    | | |	

4. 选择 **创建** 按钮开始配置和部署新的 Azure 功能应用程序。

5. 等待说明已创建资源的通知。

6. 刷新 **函数应用** 页面，并验证新资源是否在 *运行*。 

    ![带有新函数应用的“函数应用”页面的屏幕截图。](../images/0701.png)

# 任务 2：创建一个 HTTP 触发函数并对其进行测试

在此任务中，我们将通过 Webhook + API 函数在出现 HTTP 请求时显示消息。 

1. 选择新函数应用。

2. 选择 **函数** 旁边的 **+** 按钮，然后选择 **门户内**。请注意可在 Visual Studio 和 VS Code 中进行开发的其他选择。单击 **继续**。 

    ![此屏幕截图显示了如何在 Azure 门户中为“dot net 入门”窗格在 Azure Functions 中选择开发环境步骤。突出显示创建新门户内功能的显示元素。突出显示元素展开函数应用、添加新函数、门户内和继续按钮。](../images/0702.png)

3. 选择 **WebHook + API**，然后选择 **创建**。每当应用接收到 HTTP 请求时，这就会运行函数。还有大量其他模板可供选择。

    ![此屏幕截图显示了如何在 Azure 门户中为“dot net 入门”窗格在 Azure Functions 中创建函数步骤。突出显示“Webhook + api”按钮和“创建”按钮，以说明用于向 Azure Functions 添加新 Webhook 的显示元素。](../images/0703.png)

4. 请注意，该代码旨在运行 HTTP 请求和日志信息。另请注意，该函数将返回包含名称的 Hello 消息。 

    ![函数代码的屏幕截图。突出显示 Hello 消息。](../images/0704.png)

5. 从函数编辑器顶部选择 **获取函数 URL**。 

6. 将 **键** 下拉列表的值设置为 **默认值(功能键)**。然后，选择 **复制** 以复制功能 URL。 

    ![此屏幕截图显示了 Azure 门户中函数编辑器内的“获取函数 URL”窗格。突出显示显示元素获取函数 URL 按钮、设置键下拉列表和复制 URL 按钮，以指示如何从函数编辑器中获取和复制函数 URL。](../images/0705.png)

7. 将复制的函数 URL 粘贴到 Web 浏览器的地址栏中。当请求该页面时，该函数将运行。请注意指示该函数需要一个名称的消息。 

    ![“请提供一个名称”这一消息的屏幕截图。](../images/0706.png)

8. 将 **&name=yourname** 追加到 URL 的末尾。 

    **注意**：在这里，`<yourname>` 是指你指定的名字。最终 URL 将类似于 `https://azfuncxxx.azurewebsites.net/api/HttpTrigger1?code=X9xx9999xXXXXX9x9xxxXX==&name=cindy`

    ![此屏幕截图显示了 Web 浏览器的地址栏中突出显示的函数 URL 和附加的示例用户名。此外，突出显示 hello 消息和用户名，以说明主浏览器窗口中函数的输出。](../images/0707.png)

9. 在函数运行时，跟踪信息将写入 Azure 中的日志文件。要在 Azure 门户中查看日志，请返回到功能编辑器，然后选择 **日志** 按钮。

    ![此屏幕截图显示了在 Azure 门户的函数编辑器中运行函数所产生的跟踪信息日志。](../images/0709.png)

恭喜！你已创建一个函数应用，当出现 HTTP 请求时，它会显示 Hello 消息。 

**注意**：为避免产生额外费用，你可以删除此资源组。搜索资源组，单击你的资源组，然后单击 **删除资源组**。验证资源组的名称，然后单击 **删除**。关注 **通知**，了解删除操作的进度。