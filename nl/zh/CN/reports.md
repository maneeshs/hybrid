---

copyright:
  years: 2017
lastupdated: "2017-05-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:pre: .pre}
{:table: .aria-labeledby="caption"}


# 按类型列出的报告详细信息

## 防火墙登录
{: #firewalllogins}

报告与管理员登录到 Vyatta 防火墙设备相关的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>事件名称</dt>
<dd>事件的类型（用户无法通过 SSH 登录 - 密码不正确、认证失败、会话已关闭、已接受用户密码、已为用户打开会话）。
</dd>
<dt>低级别类别</dt>
<dd>事件详细信息（SSH 登录失败、会话已关闭、主机登录成功、会话已打开）。
</dd>
<dt>用户名</dt> 
<dd>启动会话的用户的凭证（用户名）。</dd>
<dt>源 IP</dt>
<dd>用户启动会话的 IP 地址。
<dt>目标 IP</dt>
<dd>会话的目标。</dd>
<dt>日志源</dt>
<dd>事件的源（生成事件的防火墙的主机名）。
</dd>
</dl>

## 防火墙拒绝
{: #firewalldenies}

报告因现有防火墙规则访问请求被拒绝时 Vyatta 防火墙设备生成的事件。
  
### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期和时间。</dd>
<dt>事件名称</dt>
<dd>事件的类型（用户无法通过 SSH 登录 - 密码不正确、认证失败、会话已关闭、已接受用户密码、已为用户打开会话）。
</dd>
<dt>低级别类别</dt>
<dd>防火墙拒绝事件的详细信息</dd>
<dt>源 IP</dt> 
<dd>网络连接和/或攻击开始的源 IP 地址。
</dd>
<dt>源端口</dt>
<dd>协议目标端口。
<dt>目标 IP</dt>
<dd>会话的目标。</dd>
<dt>目标端口</dt>
<dd>协议目标端口。
</dd>
<dt>协议</dt>
<dd>通信协议 (tcp/udp)。
<dt>日志源</dt>
<dd>事件的源（生成事件的防火墙的主机名）。
</dd>
<dt>事件计数</dt>
<dd>该类型的事件数。</dd>
</dl>

## 操作系统登录
{: #oslogin}

报告管理员在 Bluemix 系统上启动 SSH 会话时操作系统生成的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>事件名称</dt>
<dd>事件的类型（用户空间认证、用户空间认证失败）</dd>
<dt>用户名</dt> 
<dd>启动认证流程的用户的用户名。</dd>
<dt>源地址</dt>
<dd>用户启动会话的 IP 地址。
<dt>目标 IP</dt>
<dd>会话的目标。</dd>
<dt>日志源</dt>
<dd>事件的源（生成事件的服务器的主机名）。
</dd>
</dl>

## 登录服务器登录 
{: #loginserverlogins}

报告 Bluemix 平台用户使用命令行、REST API 或 Bluemix 控制台启动会话时，Bluemix 平台登录组件生成的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>事件名称</dt>
<dd>事件的类型（用户空间认证、用户空间认证失败）</dd>
<dt>用户</dt> 
<dd>启动认证流程的用户的用户标识。</dd>
<dt>Bluemix_Platform_Component</dt>
<dd>生成事件的组件 (login_server)。
<dt>消息类型</dt>
<dd>操作的类型（登录、注销）。</dd>
<dt>状态</dt>
<dd>操作的结果（成功/失败）。</dd>
<dt>日志源</dt>
<dd>事件的源。</dd>
</dl>

## 数据库管理
{: #dbadmin}

报告与数据库管理员在 Bluemix 内部数据库上执行的操作相关的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>Event_Type</dt>
<dd>事件的类型 (SECURITY_RUNTIME)。
<dt>用户</dt> 
<dd>执行操作的用户的用户名。以下用户是针对数据库定义的用户。
<ul>
<li>UAADB：vcap、root、backup_user。
</li>
<li>CCDB：vcap、ccadmin、backup_user。
</li>
<li>如有以上用户之外的使用情况，需要调查是何人执行的操作。使用“操作系统管理安全报告”和“操作系统登录安全报告”可以完成此调查。
</li>
</ul>
</dd>
<dt>源</dt> 
<dd>用户启动命令的 IP 地址。
期望值如下：
<ul>
<li>UAADB – uaa VM 和 nfs_WAL_server VM。
</li>
<li>CCDB – api_worker、clock_global、cloud_controller_ng 和 nsf_WAL_server VM。
</li>
</ul>
</dd>
<dt>DB_Statement</dt>
<dd>操作的类型（所有数据定义语句（如 CREATE、ALTER 和 DROP 语句），以及数据修改语句（如 INSERT、UPDATE、DELETE、TRUNCATE 和 COPY FROM））</dd>
<dt>DB_Name</dt>
<dd>执行操作的数据库名称</dd>
</dl>

## 管理控制台用户管理
{: #acusermgmt}

报告在 Bluemix 管理控制台上执行的用户管理活动。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>Event_Type</dt>
<dd>事件的类型 (SECURITY_RUNTIME)。
<ul>
<li>SECURITY_MGMT_REGISTRY：添加用户 [用户标识]
</li>
<li>SECURITY_MGMT_REGISTRY：删除用户 [用户标识]
</li>
<li>SECURITY_AUTHN_CREDS_MODIFY：向用户 [用户标识] 添加许可权 [许可权]。
</li>
<li>SECURITY_AUTHN_CREDS_MODIFY：从用户 [用户标识] 除去许可权 [许可权]。
</li>
<li>SECURITY_MGMT_CONFIG：创建组织 [名称]。
</li>
<li>SECURITY_MGMT_CONFIG：更改组织管理员 [标识]。
</li>
<li>SECURITY_MGMT_CONFIG：将组织标识 [标识] 重命名为新名称 [名称]。
</li>
<li>SECURITY_MGMT_CONFIG：删除组织标识 [标识]。
</li>
<li>SECURITY_MGMT_CONFIG：将组织 [标识] 的配额更新为配额 [配额套餐]。
</li>
</ul>
</dd>
<dt>用户</dt> 
<dd>启动操作的用户（LDAP 标识）。
<dt>消息</dt> 
<dd>命令已执行。
<ul>
<li>添加用户 [用户标识]：添加具有指定标识的用户。</li>
<li>删除用户 [用户标识]：删除具有指定标识的用户。</li>
<li>向用户 [用户标识] 添加许可权 [许可权]：向指定用户添加许可权。许可权可以包括：ops.admin、ops.login、ops.reports.read、ops.reports.write、ops.catalog.read、ops.catalog.write、ops.users.read 和 ops.user.write。</li>
<li>从用户 [用户标识] 除去许可权 [许可权]：除去许可权 - 从指定用户除去许可权。许可权可以包括：ops.admin、ops.login、ops.reports.read、ops.reports.write、ops.catalog.read、ops.catalog.write、ops.users.read 和 ops.users.write。</li>
<li>创建组织 [名称]：创建具有指定名称的组织。</li>
<li>更改组织管理员 [标识]：将组织管理员配置为指定的用户。</li>
<li>将组织标识 [标识] 重命名为新名称 [名称]：重命名指定的组织。</li>
<li>删除用户 [用户标识]：删除具有指定标识的用户。</li>
<li>删除组织标识 [标识]：删除指定的组织。</li>
<li>将组织 [标识] 的配额更新为配额 [配额套餐]：更新指定组织的配额套餐。套餐可以包括：q2GB、q4GB、q8GB、q16GB、q32GB、q64GB、q128GB、q256GB、q512GB。
</li>
</ul>
</dd>
<dt>日志源</dt>
<dd>事件的源（生成事件的服务器的 IP 地址/主机名）</dd>
</dl>

## 目录管理
{: #catalogmgmt}

报告与在 Bluemix 管理控制台上执行的服务目录管理活动相关的事件。 

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>SECURITY_MGMT_CONFIG</dt>
<dd>注册模板 [标识]。使具有指定标识的样板或运行时在目录中对所有用户显示为选项。</dd>
<dd>取消注册模板 [标识]。使样板或运行时在目录中不再对所有用户显示为选项。</dd>
<dd>将服务套餐 [标识] 更新为公共 = [ public ] 且可视性 = [ 标识 ]。更新指定服务套餐的可视性。如果公共设置为 true，那么所有组织都可看到套餐。如果公共设置为 false，那么可能会提供一组组织标识，以指出哪些组织可以看到此服务套餐。</dd>
<dd>添加服务代理程序 [名称]。添加具有指定名称的服务代理程序。</dd>
<dd>删除服务代理程序 [名称]。删除具有指定名称的服务代理程序。</dd>
<dd>更新 buildpack [标识]。针对具有指定标识的 buildpack 更新 buildpack 顺序。</dd>
<dt>日志源</dt>
<dd>事件的源（生成事件的服务器的 IP 地址/主机名）</dd>
</dl>

## 安全报告管理
{: #securityreportsmgmt}

报告与在管理控制台上执行的安全报告管理活动相关的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dd>事件的类型 (SECURITY_RUNTIME)。
<ul>
<li>SECURITY_DATA_SYNC：将报告 [名称] 上传到类别 [名称] 日期 [日期]。
删除标识为 [标识] 的报告
</li>
<li>SECURITY_RESOURCE_ACCESS：下载报告 [名称]。
</li>
</ul>
</dd>
<dt>用户</dt> 
<dd>启动操作的用户。
<dt>消息</dt> 
<dd>命令已执行。
<ul>
<li>将报告 [名称] 上传到类别 [名称] 日期 [日期]：上传 - 将具有指定文件名和日期的报告上传到指定的类别。</li>
<li>删除标识为 [标识] 的报告：删除 - 删除具有指定标识的报告。</li>
<li>下载报告 [名称]：下载 - 已下载具有指定名称的报告。</li>
</ul>
</dd>
<dt>日志源</dt>
<dd>事件的源（生成事件的服务器的 IP 地址/主机名）</dd>
</dl>

## 访问审核
{: #accessreviews}

报告对 Bluemix 环境的特权访问请求，以及 Bluemix 管理员对它们的处理。 

### 数据字段

<dl>
<dt>Action_Name</dt>
<dd>指出用户的以下请求：成为组的一部分、重命名用户标识、撤销以防解除或从组除去（添加、重命名、撤销、删除）。</dd>
<dt>状态</dt>
<dd>此字段指出请求的状态。核准人接受或拒绝请求。请求待核准。用户取消请求（已接受、已拒绝、待核准、已取消）。</dd>
<dt>Id_User</dt>
<dd>用户名</dd>
<dt>User_name</dt> 
<dd>发出请求的用户。</dd>
<dt>Manager_Approval</dt>
<dd>管理员核准请求的日期
<dt>Access_Approval</dt>
<dd>组管理员核准请求的日期。
</dd>
</dl>

## 密钥管理
{: #keymgmt}

报告密钥证书管理操作。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>Event_Name</dt>
<dd>事件的类型（创建密钥、创建证书、删除证书）。</dd>
<dt>证书/密钥名称</dt>
<dd>使用的证书名称或密钥名称。</dd>
<dt>Key_Mgmt_Message</dt> 
<dd>命令已执行（创建密钥“密钥名称”、创建证书“证书名称”、证书“证书名称”配置已删除）。</dd>
<dt>目标 IP</dt>
<dd>会话的目标。
<dt>日志源</dt>
<dd>事件的源。</dd>
</dl>

## 系统通知
{: #systemnotifications}

报告与配置软件更新部署窗口或通知预订相关的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>Event_Type</dt>
<dd>事件的类型 (SECURITY_RUNTIME)。
<ul>
<li> SECURITY_MGMT_CONFIG：创建窗口 [标识]。
</li>
<li> SECURITY_MGMT_CONFIG：更新窗口 [标识]。
</li>
<li> SECURITY_MGMT_CONFIG：删除窗口 [标识]。
</li>
<li> SECURITY_MGMT_CONFIG：创建预订 [标识]。
</li>
<li> SECURITY_MGMT_CONFIG：更新预订 [标识]。
</li>
<li> SECURITY_MGMT_CONFIG：删除预订 [标识]。
</li>
<li> SECURITY_MGMT_CONFIG：创建主题回复 [标识]。
</li>
</ul>
</dd>
<dt>用户</dt> 
<dd>启动操作的用户
<dt>消息</dt>
<dd>命令已执行。
<ul>
<li>创建窗口 [标识]：创建用于维护更新的窗口。用户在管理（创建）环境的更新窗口时，将生成更新窗口日志。更新窗口是用于部署的中断和首选窗口。当客户在无需核准和安排非中断性部署的情况下，允许或不允许进行此类部署时生成此事件。
</li>
<li>更新窗口 [标识]：更新维护更新窗口。用户更新环境的维护更新窗口时，会生成此事件。
</li>
<li>SECURITY_MGMT_CONFIG：删除更新窗口。用户委派环境的更新窗口时，会生成此事件。
</li>
<li>创建预订 [标识]：创建事件预订。用户为更新事件或事故事件创建预订时，会生成事件预订审计日志。这样一来，当用户的系统上发生某些状况时，用户就可以获得通知。</li>
<li>更新预订 [标识]：更新事件预订。用户为更新事件或事故事件更新预订时，会生成此事件。</li>
<li>删除预订 [标识]：删除事件预订。用户为更新事件或事故事件删除预订时，会生成此事件。</li>
<li>创建主题回复 [标识]：回复主题。客户核准并安排中断性更新时，会生成主题回复审计日志。</li>
</ul>
</dd>
<dt>日志源</dt>
<dd>事件的源（生成事件的服务器的 IP 地址/主机名）。</dd>
</dl>

## Bluemix 平台管理
{: #platformadmin}

报告与使用命令行、REST API 或 Bluemix 用户界面的 Bluemix 平台相关的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>Event_Type</dt>
<dd>事件的类型 (SECURITY_RUNTIME)。
<ul>
<li>SECURITY_AUTH_CREDS_MODIFY：与修改给定用户身份的凭证相关的事件。
</li>
<li>SECURITY_MGMT_RESOURCE：资源管理事件（如创建、删除和更改资源的属性）。
</li>
<li>SECURITY_MGMT_POLICY：与管理安全策略相关的事件（如创建访问控制表）。</li>
<li>SECURITY_RUNTIME：运行时事件（如安全服务器的启动和停止）。
</li>
<li>SECURITY_RESOURCE_ACCESS：记录资源所有访问的事件。示例为对文件的所有访问、对给定 Web 页面的所有 HTTP 请求/响应，以及对关键数据库表的所有访问。
</li>
</ul>
</dd>
<dt>用户</dt> 
<dd>启动操作的用户
<dt>目标</dt> 
<dd>执行的操作的详细信息，如实体的标识和操作的结果。示例：<ul>
<li>UserCreatedEvent ('["user_id=ca3a811f-1778-4103-9553-537788ed4c4e","username=equaranta"]’)。创建了用户名为 equaranta、标识为 ca3a811f-1778-4103-9553-537788ed4c4e 的用户。
</li>
<li>GroupModifiedEvent ('{" "group_name":"ops.reports.read","members":["0625ff9a- 8a59-4cca-a80a-8e3b51f3dd21","5005f0f8-e090-4cabb51d- 2ceee70acf0e"}')。修改了名称为 ops.reports.read 的组，生成的成员资格为：(id 0625ff9a- 8a59-4ccaa80a- 8e3b51f3dd21","5005f0f8- e090-4cab-b51d- 2ceee70acf0e)。
</li>
<li>UserDeletedEvent ('["UserDeletedEvent ('["user_id=5cd5f412-4bbb-4c44-b44b- 713a5bc6144d","username=818811853"]'):"]'。删除了标识值为 5cd5f412-4bbb- 4c44-b44b-713a5bc6144 的用户。
</li>
</ul>
</dd>
<dt>消息</dt>
<dd>执行操作的实体（消息字符串）或操作的标准 HTTP 返回码（数字值）。</dd>
<dt>Bluemix_Platform_Component</dt>
<dd>组件名称。</dd>
<dt>日志源</dt>
<dd>事件源的主机名/IP 地址。</dd>
<dt>源</dt>
<dd>事件和示例的源为 IP 地址。</dd>
<dt>数据</dt>
<dd>其他详细信息。</dd>
</dl>

## 操作系统管理
{: #osadmin}

报告 Bluemix 生成的可帮助诊断故障（例如，Bosh 代理程序无法部署或服务未启动）的事件。

### 数据字段

<dl>
<dt>日志源时间</dt>
<dd>事件发生的日期。</dd>
<dt>Event_Name</dt>
<dd>事件的类型（创建密钥、创建证书、删除证书）。</dd>
<dt>BMX_key</dt>
<dd>操作的类型（BMX_executed_command、BMX_access_unauthorized、BMX_unsuccessful_delete、BMX_sudoers_folder、BMX_Identity_shadow、BMX_extended_attribute、BMX_sudoers）。</dd>
<dt>auid</dt> 
<dd>登录的用户的源用户标识（例如，auid=0 为 root、auid=1000 为 vcap、auid= 55044 为 ldap 用户）。</dd>
<dt>uid</dt>
<dd>运行命令时使用的目标用户标识（例如，在运行命令之前，auid=55044 登录并执行“sudo su”(root) -> uid=0）。
<dt>exe_key</dt>
<dd>执行的命令。</dd>
<dt>源 IP</dt>
<dd>用户启动命令的 IP 地址。
</dd>
<dt>日志源</dt>
<dd>事件的源。</dd>
</dl>
