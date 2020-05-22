---
UID: NC:wdfsync.PFN_WDFOBJECTRELEASELOCK
title: PFN_WDFOBJECTRELEASELOCK (wdfsync.h)
description: The WdfObjectReleaseLock method releases an object's synchronization lock.
old-location: wdf\wdfobjectreleaselock.htm
tech.root: wdf
ms.assetid: a2fe9393-1525-47d7-94e1-1886ea54e270
ms.date: 01/11/2018
keywords: ["PFN_WDFOBJECTRELEASELOCK callback"]
ms.keywords: wdf.wdfobjectreleaselock, PFN_WDFOBJECTRELEASELOCK, WdfObjectReleaseLock callback function, WdfObjectReleaseLock, wdfsync/WdfObjectReleaseLock, DFSynchroRef_14ab9c69-1eb8-4a83-b1fb-cb8db7a67d06.xml, kmdf.wdfobjectreleaselock
f1_keywords:
 - "wdfsync/WdfObjectReleaseLock"
req.header: wdfsync.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdfsync.h
api_name:
- WdfObjectReleaseLock
product:
- Windows
targetos: Windows
req.typenames: "*PWDF_REQUEST_SEND_OPTIONS, WDF_REQUEST_SEND_OPTIONS"
req.product: Windows 10 or later.
---

# WdfObjectReleaseLock callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfObjectReleaseLock</b> method releases an object's synchronization lock.


## -prototype


```cpp
VOID WdfObjectReleaseLock(
  _In_ WDFOBJECT Object
);
```


## -parameters




### -param DriverGlobals



### -param WDFOBJECT






#### - Object [in]

A handle to a framework device object or a framework queue object.




## -remarks

A bug check occurs if the driver supplies an invalid object handle.

The <b>WdfObjectReleaseLock</b> method releases the synchronization lock that a driver acquired by previously calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548721">WdfObjectAcquireLock</a>. <b>WdfObjectReleaseLock</b> also restores the driver's IRQL to the value that it had before the driver called <b>WdfObjectAcquireLock</b>.

For more information about synchronization locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548721">WdfObjectAcquireLock</a>

 

 


