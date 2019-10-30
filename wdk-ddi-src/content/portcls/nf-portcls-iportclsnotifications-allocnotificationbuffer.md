---
UID: NF:portcls.IPortClsNotifications.AllocNotificationBuffer
title: IPortClsNotifications::AllocNotificationBuffer (portcls.h)
description: Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps.
old-location: audio\iportclsnotifications_allocnotification.htm
tech.root: audio
ms.assetid: 23DBA3D8-FC27-4F5D-9F1C-A22B6C2856D2
ms.date: 05/08/2018
ms.keywords: AllocNotificationBuffer, AllocNotificationBuffer method [Audio Devices], AllocNotificationBuffer method [Audio Devices],IPortClsNotifications interface, IPortClsNotifications interface [Audio Devices],AllocNotificationBuffer method, IPortClsNotifications.AllocNotificationBuffer, IPortClsNotifications::AllocNotificationBuffer, audio.iportclsnotifications_allocnotification, portcls/IPortClsNotifications::AllocNotificationBuffer
ms.topic: method
f1_keywords:
 - "portcls/IPortClsNotifications.AllocNotificationBuffer"
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- IPortClsNotifications.AllocNotificationBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortClsNotifications::AllocNotificationBuffer


## -description


Allocates a buffer of the specified size, in the specified memory pool, for use in sending notifications, to allow for communications between audio modules and UWP apps. 

For more information about audio modules, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/implementing-audio-module-communication">Implementing Audio Module Discovery</a>. 


## -parameters




### -param PoolType [in]

Specifies the type of memory pool from which the object is to be allocated (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_pool_type">POOL_TYPE</a>). The recommended values are NonPagedPoolNx or PagedPool. The memory pool type selection also depends on the IRQL level. If running at DISPATCH_LEVEL the memory must be non-paged.


### -param NumberOfBytes [in]

Number of bytes to allocate.


### -param NotificationBuffer [out]

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/ns-portcls-_pcnotification_buffer">PCNOTIFICATION_BUFFER</a> which the method writes the address of the allocated notification.


## -returns



STATUS_SUCCESS – The driver was able to allocate the notification buffer. 

   



STATUS_INVALID_PARAMETER – The driver returns this error if it finds any other parameter invalid, aside from the specific cases for other error status instances. 



Additional standard status codes may be returned. For example, STATUS_INSUFFICIENT_RESOURCES will be returned if it is not possible to allocate the required buffer.




## -remarks



Callers of <b>AllocNotificationBuffer</b> must be running at IRQL <= DISPATCH_LEVEL. If a driver writer calls this routine at IRQL = DISPATCH_LEVEL, the NotificationStructure must be allocated from nonpaged memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iportclsnotifications">IPortClsNotifications</a>
 

 

