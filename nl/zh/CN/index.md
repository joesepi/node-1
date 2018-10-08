---

copyright:
  years: 2018
lastupdated: "2018-09-10"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}

# 入门教程

以下教程指导您完成使用 {{site.data.keyword.cloud_notm}} 提供的工具来构建、本地运行和部署 Node.js 应用程序的步骤。您可以在命令行上使用 [{{site.data.keyword.dev_cli_long}}](https://console.bluemix.net/docs/cloudnative/dev_cli.html#add-cli) 或使用基于 Web 的 [{{site.data.keyword.cloud}} {{site.data.keyword.dev_console}}](https://console.bluemix.net/developer/appservice/dashboard)，如以下教程步骤中所示。通过使用这其中任一种方法，您可以在仅仅几分钟内就生成生产就绪型 Node.js 应用程序。

确保使用的是最新的 Node.js LTS 发行版。

## 创建 Node.js 应用程序
{: #create_project}

1. 在 {{site.data.keyword.dev_console}} 中的[入门模板工具包](https://console.bluemix.net/developer/appservice/starter-kits)页面中，选择使用 `Node.js` 编写的入门模板工具包。此外，还可以通过单击**创建应用程序**并选择 `Node.js` 作为语言来创建空白的入门模板应用程序。

    您必须登录到 {{site.data.keyword.cloud_notm}} 帐户才能创建项目。如果您没有帐户，那么可以[注册免费帐户](https://console.bluemix.net/registration)。
    {: tip}

2. 单击**创建应用程序**。
3. 对应用程序**命名**。系统会提供通用应用程序名称（如果您要使用此名称）。
4. 输入**唯一主机名**。主机名用于访问应用程序，例如：`expressjs-project.mybluemix.net`。
5. 单击**创建**。创建项目后，可以使用工具链进行部署，也可以继续构建，然后通过命令行部署项目。
6. 如果选择创建工具链，请单击**部署到云**，然后选择下列其中一种部署方法。
    * **Cloud Foundry 应用程序** - 您无需管理底层基础架构。
    * **Kubernetes 集群** - 您必须供应一组工作程序节点。例如，可以使用 VM 来部署和管理高可用性应用程序容器。可以创建集群或部署到现有集群。

7. 完成选项，然后单击**创建**以创建工具链。

8. 如果选择继续使用 CLI 而不使用工具链，请将项目下载到本地计算机，对项目执行 `unzip` 命令，然后通过 `cd` 命令转至根目录。现在，可以使用以下平台命令方法来安装必备软件：

    MacOS：
    ```
    curl -sL https://ibm.biz/idt-installer | bash
    ```
    {: codeblock}

    Windows（以管理员身份运行）：
    ```
    Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
    ```
    {: codeblock}

## 添加服务
{: #add_service}

1. 返回到 {{site.data.keyword.cloud_notm}} {{site.data.keyword.dev_console}} 中您的项目。
2. 单击**添加服务**，选择要添加的服务的类别，单击**下一步**，然后选择服务。例如，要将 NoSQL 数据库添加到应用程序中，请单击“数据”类别，然后选择 Cloudant；Cloudant 提供有轻量套餐，可进行免费开发。{{site.data.keyword.cloud_notm}} {{site.data.keyword.dev_console}} 会根据所选套餐供应服务。
注：如果先前已供应您计划使用的服务，请选择**现有**类别。
3. 供应服务后，单击**下载代码**以使用连接到服务的 SDK 重新生成项目。

<!--
<video of creating a project and adding a service>
-->

## 本地运行应用程序
{: #run_local}

1. 使用 `ibmcloud dev build` 命令构建应用程序。
2. 使用 `ibmcloud dev run` 命令在本地运行应用程序。应用程序将在本地系统上的 Docker 容器中运行。可以在浏览器中通过访问 `http://localhost:3000` 来测试应用程序。
3. `http://localhost:3000/health` 上提供了运行状况检查端点。
4. 可以访问 [App Metrics](https://developer.ibm.com/node/monitoring-post-mortem/application-metrics-node-js/) 仪表板：`http://localhost:3000/appmetrics-dash`。

<!--
<video>
-->

## 部署到云
{: #deploy_cloud}

使用 `ibmcloud dev deploy` 命令作为 Cloud Foundry 应用程序部署到 {{site.data.keyword.cloud_notm}}。 

要部署到 {{site.data.keyword.cloud_notm}} 中的 IBM Container Services，请使用以下命令：
```
ibmcloud dev deploy –target container 
```
{: codeblock}

## 后续步骤
{: #nextsteps}

继续查看有关 Node.js 编程指南的主题，或者要获取更高级部署的信息，可以了解如何创建 Kubernetes 集群并将 Node.js 应用程序部署到该集群。

### 设置 Kubernetes 集群
有关在 {{site.data.keyword.cloud_notm}} 中设置 Kubernetes 集群的更多信息，请查看[教程步骤](https://console.bluemix.net/docs/containers/cs_clusters.html#clusters)。

### 将 Node.js 应用程序部署到 Kubernetes 集群
了解如何[将 Node.js 应用程序部署到 Kubernetes 集群](../containers/cs_tutorials_apps.html)。