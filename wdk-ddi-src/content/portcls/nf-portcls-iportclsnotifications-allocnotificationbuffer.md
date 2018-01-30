---
UID: NF:portcls.IPortClsNotifications.AllocNotificationBuffer
title: IPortClsNotifications::AllocNotificationBuffer method
author: windows-driver-content
description: Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps.
old-location: audio\iportclsnotifications_allocnotification.htm
old-project: audio
ms.assetid: 23DBA3D8-FC27-4F5D-9F1C-A22B6C2856D2
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: portcls/IPortClsNotifications::AllocNotificationBuffer, AllocNotificationBuffer method [Audio Devices], IPortClsNotifications::AllocNotificationBuffer, audio.iportclsnotifications_allocnotification, IPortClsNotifications interface [Audio Devices], AllocNotificationBuffer method, IPortClsNotifications, AllocNotificationBuffer method [Audio Devices], IPortClsNotifications interface, AllocNotificationBuffer
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	IPortClsNotifications.AllocNotificationBuffer
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPortClsNotifications::AllocNotificationBuffer method


## -description


Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. 

For more information about audio modules, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 


## -syntax


````
NTSTATUS  AllocNotificationBuffer(
  [in]  POOL_TYPE    PoolType,
  [in]  USHORT       NumberOfBytes,
  [out] Notification PPCNOTIFICATION* 
);
````


## -parameters




### -param PoolType [in]

Specifies the type of memory pool from which the object is to be allocated (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559707">POOL_TYPE</a>). The recommended values are NonPagedPoolNx or PagedPool. The memory pool type selection also depends on the IRQL level. If running at DISPATCH_LEVEL the memory must be non-paged.


### -param NumberOfBytes [in]

Number of bytes to allocate.


### -param NotificationBuffer





#### - PPCNOTIFICATION* [out]

Pointer to a <a href="..\portcls\ns-portcls-_pcnotification_buffer.md">PCNOTIFICATION_BUFFER</a> which the method writes the address of the allocated notification.


## -returns


STATUS_SUCCESS – The driver was able to allocate the notification buffer. 

   



STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned. For example, STATUS_INSUFFICIENT_RESOURCES will be returned if it is not possible to allocate the required buffer.



## -remarks


Callers of <b>AllocNotificationBuffer</b> must be running at IRQL &lt;= DISPATCH_LEVEL. If a driver writer calls this routine at IRQL = DISPATCH_LEVEL, the NotificationStructure must be allocated from nonpaged memory.



## -see-also

<a href="..\portcls\nn-portcls-iportclsnotifications.md">IPortClsNotifications</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortClsNotifications::AllocNotificationBuffer method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

