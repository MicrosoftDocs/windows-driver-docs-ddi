---
UID: NN:portcls.IPortClsNotifications
title: IPortClsNotifications
author: windows-driver-content
description: An interface implemented by ports to provide notification helpers to miniports to support audio module communication.
old-location: audio\iportclsnotifications.htm
old-project: audio
ms.assetid: 03F65E4E-C942-4748-8D3E-938A6AC51B2A
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: audio.iportclsnotifications, IPortClsNotifications interface [Audio Devices], IPortClsNotifications interface [Audio Devices], described, IPortClsNotifications, portcls/IPortClsNotifications
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPortClsNotifications
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IPortClsNotifications interface


## -description


An interface implemented by ports to provide
 notification helpers to miniports to support audio module communication.

For more information about audio modules, 
 see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 
 

The miniport audio driver will call into their port to create and send the notification.  


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
</table>Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. 

Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. 

Sends a notification to the listening UWP apps, to allow for communications between audio modules and UWP apps. 

 

