﻿---
title: 在 Lync Server 2013 中创建语音路由
TOCTitle: 在 Lync Server 2013 中创建语音路由
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398898(v=OCS.15)
ms:contentKeyID: 49314319
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建语音路由

 

_**上一次修改主题：** 2016-12-08_

以下过程将介绍如何使用 Lync Server 2013 控制面板创建新语音路由。要编辑现有路由，请参阅[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)中的相关步骤。

## 使用 Lync Server 控制面板创建语音路由

1.  以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”。

4.  单击“路由”。

5.  单击“新建”以显示“新建语音路由”对话框。

6.  在“名称”中，键入语音路由的描述性名称。

7.  （可选）在“说明”中，为语音路由键入其他描述性信息。

8.  要指定希望此路由满足的模式，可以使用“建立匹配的模式”工具生成正则表达式，或手动写入正则表达式。
    
      - 要使用“建立匹配的模式”工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
        
          - **希望允许的号码起始数字：** 输入此路由必须满足的前缀值（如有必要，包括前导 +）。例如，键入 **+425**，然后单击“添加”。对希望包含在路由中的每个前缀值重复此过程。
        
          - **例外：** 如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击“例外”。为*不* 希望此路由满足的匹配模式键入一个或多个值。例如，要从路由中排除以 +425237 开头的号码，请在“例外”字段中输入值 **+425237**，然后单击“确定”。
    
      - 若要手动定义匹配模式，请在“构建要匹配的模式”工具中单击“编辑”，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。有关如何编写正则表达式的详细信息，请参阅“.NET Framework 正则表达式”，网址为 [http://go.microsoft.com/fwlink/?linkid=140927\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=140927%26clcid=0x804)。

9.  如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”。如果选择此选项，必须指定显示在接收人的呼叫者 ID 显示器上的“备用呼叫者 ID”。

10. 要将一个或多个中继与语音路由相关联，请单击“添加”，然后从列表中选择中继。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Dn783119.note(OCS.15).gif" title="note" alt="note" />注意：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>如果部署包括任何 Microsoft Office Communications Server 2007 R2 中介服务器，则它们也会显示在该列表中。</td>
    </tr>
    </tbody>
    </table>


11. 要将一个或多个公用电话交换网 (PSTN) 用法记录与语音路由相关联，请单击“选择”，然后从已为企业语音部署定义的 PSTN 用法记录列表中选择一条记录。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Dn783119.note(OCS.15).gif" title="note" alt="note" />注意：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>要查看每个可用 PSTN 用法记录的属性，请参阅<a href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 用法记录</a>。<br />
    要创建或编辑 PSTN 用法记录，请参阅<a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录</a>或<a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录</a>。</td>
    </tr>
    </tbody>
    </table>


12. 排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Dn783119.note(OCS.15).gif" title="note" alt="note" />注意：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>在语音策略中，PSTN 用法记录的列出顺序非常重要，而在语音路由中，PSTN 用法记录的列出顺序则无关紧要。但是，建议您按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。（Lync Server 按照从上到下的顺序遍历该列表。）</td>
    </tr>
    </tbody>
    </table>


13. （可选）在“输入转换后的号码以进行测试”字段中键入一个值，然后单击“执行”。测试结果将显示在该字段下面。
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Dn783119.note(OCS.15).gif" title="note" alt="note" />注意：</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>您可以保存尚未通过测试的语音路由，并在稍后对其进行重新配置。有关详细信息，请参阅<a href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</a>。</td>
    </tr>
    </tbody>
    </table>


14. 单击“确定”保存语音路由。

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398794.important(OCS.15).gif" title="important" alt="important" />重要提示：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>任何时候创建语音路由，都必须运行“全部提交”命令以发布配置更改。有关详细信息，请参阅<a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中发布对语音路由配置所做的待处理更改</a>。</td>
</tr>
</tbody>
</table>


## 另请参阅

#### 任务

[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)  
[在 Lync Server 2013 中查看 PSTN 用法记录](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的待处理更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  

#### 其他资源

[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)

