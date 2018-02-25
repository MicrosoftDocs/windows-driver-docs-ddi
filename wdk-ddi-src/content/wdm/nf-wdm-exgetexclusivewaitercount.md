---
UID: NF:wdm.ExGetExclusiveWaiterCount
title: ExGetExclusiveWaiterCount function
author: windows-driver-content
description: The ExGetExclusiveWaiterCount routine returns the number of waiters on exclusive access to a given resource.
old-location: kernel\exgetexclusivewaitercount.htm
old-project: kernel
ms.assetid: 032989b7-ba61-4cb3-b6b5-ac66124cdd79
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, E, ExGetExclusiveWaiterCount, ExGetExclusiveWaiterCount routine [Kernel-Mode Driver Architecture], G, W, a, c, e, i, k102_bd65d9e8-06bf-4492-88f1-bfd4e46fb29e.xml, kernel.exgetexclusivewaitercount, l, n, o, r, s, t, u, v, wdm/ExGetExclusiveWaiterCount, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ExGetExclusiveWaiterCount
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExGetExclusiveWaiterCount function


## -description


The <b>ExGetExclusiveWaiterCount</b> routine returns the number of waiters on exclusive access to a given resource.


## -syntax


````
ULONG ExGetExclusiveWaiterCount(
  _In_ PERESOURCE Resource
);
````


## -parameters




### -param Resource [in]

A pointer to the resource to be tested.


## -returns



<b>ExGetExclusiveWaiterCount</b> returns the number of threads currently waiting to acquire the given resource for exclusive access.




## -remarks



<b>ExGetExclusiveWaiterCount</b> can be called to get an estimate of how many other threads might be waiting to modify the data protected by a particular resource variable. The caller cannot assume that the returned value remains constant for any particular interval.




## -see-also

<a href="..\wdm\nf-wdm-exgetsharedwaitercount.md">ExGetSharedWaiterCount</a>



<a href="..\wdm\nf-wdm-exacquiresharedwaitforexclusive.md">ExAcquireSharedWaitForExclusive</a>



<a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>



<a href="..\wdm\nf-wdm-exacquiresharedstarveexclusive.md">ExAcquireSharedStarveExclusive</a>



<a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a>



<a href="..\wdm\nf-wdm-exacquireresourceexclusivelite.md">ExAcquireResourceExclusiveLite</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExGetExclusiveWaiterCount routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

