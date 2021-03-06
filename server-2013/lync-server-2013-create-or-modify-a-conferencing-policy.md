﻿---
title: 在 Lync Server 2013 中创建或修改会议策略
TOCTitle: 在 Lync Server 2013 中创建或修改会议策略
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49888650
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改会议策略

 

_**上一次修改主题：** 2013-02-07_

按照以下步骤创建用户级别或站点级别会议策略。有关如何将用户级别策略分配到用户的详细信息，请参阅[分配每用户会议策略](lync-server-2013-assign-a-per-user-conferencing-policy.md)。有关所有可用会议策略设置的列表，请参阅[在 Lync Server 2013 中会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。

## 创建新的用户或站点策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议策略”。

4.  单击“新建”，然后执行以下操作之一：
    
      - 要创建用户级别的策略，请单击“用户策略”。在“新建会议策略”中的“名称”字段，键入策略的描述性名称。
    
      - 要创建站点级别的策略，请单击“站点策略”。在“选择站点”搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“确定”。
        
        <table>
        <thead>
        <tr class="header">
        <th><img src="images/Dn783119.note(OCS.15).gif" title="note" alt="note" />注意：</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td>站点名称将成为会议策略名称，且无法更改。</td>
        </tr>
        </tbody>
        </table>


5.  在“说明”中，键入策略的说明。

6.  在“组织者策略”下的“最大会议大小”中，键入允许参加一次会议的最大用户数。默认情况下，最大会议大小为 250。

7.  要阻止用户邀请匿名用户参加会议，请清除“允许参与者邀请匿名用户”复选框。匿名用户指的是在组织的 Active Directory 域服务中没有凭据，因此未经过身份验证的用户。默认情况下，用户可以邀请匿名用户参加会议。

8.  在“录制”中，执行下列操作之一：
    
      - 要阻止参与者录制会议，请单击“无”。这是默认设置。
    
      - 要允许参与者录制会议，请单击“启用录制”。

9.  要允许外部参与者录制会议，请选中“允许联盟参与者和匿名参与者录制”复选框。默认为阻止外部参与者录制会议。

10. 在“音频/视频”中，执行下列操作之一：
    
      - 要阻止使用音频和视频，请单击“无”。
    
      - 要允许使用音频但不允许使用视频，请单击“启用 IP 音频”。
    
      - 要允许使用音频和视频，请单击“启用 IP 音频/视频”。这是默认设置。

11. 如果在“音频/视频”中选择允许使用音频，请执行下列操作：
    
      - 要阻止用户通过电话拨入加入会议，请清除“启用 PSTN 电话拨入式会议”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。
    
      - 如果您允许用户通过电话拨入加入会议并允许未经身份验证的（匿名）用户通过拨出式电话加入会议，请选中“允许匿名参与者拨出”复选框。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。默认情况下，匿名用户无法通过拨出式电话加入会议。

12. 如果您选择允许使用“音频/视频”中的视频，请选中“允许多个视频流”。

13. 在“数据协作”中，执行下列操作之一：
    
      - 要阻止数据协作，请单击“无”。
    
      - 要允许数据协作，请单击“启用数据协作”。这是默认设置。

14. 如果在“数据协作”中选择允许数据协作，请执行下列操作：
    
      - 要阻止外部下载，请清除“允许联盟参与者和匿名参与者下载内容”复选框。默认情况下，外部用户可以下载内容。
    
      - 要阻止文件传输，请清除“允许参与者传输文件”复选框。默认情况下，用户可以传输文件。
    
      - 要阻止使用批注，请清除“启用批注”复选框。要使用共享的 PowerPoint 演示文稿中的批注，请清除“启用 PowerPoint 批注”。默认情况下，允许使用批注。
    
      - 要阻止使用投票，请清除“启用投票”复选框。默认情况下，允许使用投票。

15. 在“应用程序共享”中，执行下列操作之一：
    
      - 要阻止使用应用程序共享，请单击“禁用应用程序共享”。
    
      - 要允许使用应用程序共享，请单击“启用应用程序共享”。这是默认设置。

16. 如果在“应用程序共享”中选择允许应用程序共享，请执行下列操作：
    
      - 要阻止会议参与者控制应用程序共享，请清除“允许参与者获得控制权”复选框。默认情况下，参与者可以控制应用程序共享。
    
      - 如果选择允许会议参与者控制应用程序共享，请选中“允许联盟参与者和匿名参与者获得控制权”复选框以允许外部用户控制应用程序共享。默认情况下，外部用户不能控制应用程序共享。

17. 在“参与者策略”下，执行下列操作之一：
    
      - 要同时阻止应用程序共享和桌面共享，请单击“禁用应用程序共享和桌面共享”。
    
      - 要允许应用程序共享但不允许桌面共享，请单击“启用应用程序共享”。
    
      - 要同时允许应用程序共享和桌面共享，请单击“启用应用程序共享和桌面共享”。这是默认设置。

18. 要阻止对等文件传输，请清除“启用对等文件传输”复选框。默认情况下，允许对等文件传输。

19. 要允许对等录制，请选中“启用对等录制”复选框。默认情况下，不允许对等录制。

20. 要允许参与者加入多个视频流，请选中“允许参与者加入多个视频流”复选框，默认情况下，允许多个视频流。

21. 单击“提交”。

## 修改现有用户或站点策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议策略”。

4.  在会议策略列表中，单击要更改的策略，单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑会议策略”中，修改任意策略设置（不能修改的策略名称除外）。

6.  单击“提交”。

