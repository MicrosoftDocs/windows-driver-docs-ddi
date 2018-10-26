---
UID: NN:portcls.IPortClsNotifications
title: IPortClsNotifications
author: windows-driver-content
description: An interface implemented by ports to provide notification helpers to miniports to support audio module communication.
old-location: audio\iportclsnotifications.htm
tech.root: audio
ms.assetid: 03F65E4E-C942-4748-8D3E-938A6AC51B2A
ms.date: 05/08/2018
ms.keywords: IPortClsNotifications, IPortClsNotifications interface [Audio Devices], IPortClsNotifications interface [Audio Devices],described, audio.iportclsnotifications, portcls/IPortClsNotifications
ms.topic: interface
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1703 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortClsNotifications
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsNotifications interface


## -description


An interface implemented by ports to provide
 notification helpers to miniports to support audio module communication.

For more information about audio modules, 
 see <a href="https://msdn.microsoft.com/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 
 

The miniport audio driver will call into their port to create and send the notification.  


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortClsNotifications</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPortClsNotifications</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortClsNotifications</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/23DBA3D8-FC27-4F5D-9F1C-A22B6C2856D2">IPortClsNotifications::AllocNotificationBuffer</a>
</td>
<td align="left" width="63%">
Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/93EC2651-3C52-4810-9F7A-A81BC7DA20AF">IPortClsNotifications::FreeNotificationBuffer</a>
</td>
<td align="left" width="63%">
Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. 

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0683C30D-0AAD-4859-BA30-908FA747CC35">IPortClsNotifications::SendNotification</a>
</td>
<td align="left" width="63%">
Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps. 

</td>
</tr>
</table> 

