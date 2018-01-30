---
UID: NF:portcls.IPortClsNotifications.FreeNotificationBuffer
title: IPortClsNotifications::FreeNotificationBuffer method
author: windows-driver-content
description: Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps.
old-location: audio\iportclsnotifications_freenotification.htm
old-project: audio
ms.assetid: 93EC2651-3C52-4810-9F7A-A81BC7DA20AF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.iportclsnotifications_freenotification, IPortClsNotifications::FreeNotificationBuffer, portcls/IPortClsNotifications::FreeNotificationBuffer, FreeNotificationBuffer method [Audio Devices], FreeNotificationBuffer method [Audio Devices], IPortClsNotifications interface, IPortClsNotifications, IPortClsNotifications interface [Audio Devices], FreeNotificationBuffer method, FreeNotificationBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
-	Portcls.lib
-	Portcls.dll
apiname:
-	IPortClsNotifications.FreeNotificationBuffer
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsNotifications::FreeNotificationBuffer method


## -description


Frees a previously allocated IPortClsNotifications buffer. The buffer is used in sending notifications, to allow for communications between audio modules and UWP apps. 

For more information about audio modules, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 


## -syntax


````
NTSTATUS  FreeNotificationBuffer(
  [in] PPCNOTIFICATION  Notification
);
````


## -parameters




### -param NotificationBuffer





#### - Notification [in]

The address of the notification buffer returned in the <a href="https://msdn.microsoft.com/23DBA3D8-FC27-4F5D-9F1C-A22B6C2856D2">IPortClsNotifications::AllocNotificationBuffer</a> call.


## -returns


This function returns void.



## -see-also

<a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsNotifications::FreeNotificationBuffer method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

