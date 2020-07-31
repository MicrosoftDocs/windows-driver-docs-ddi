---
UID: NF:wdm.ExGetSharedWaiterCount
title: ExGetSharedWaiterCount function (wdm.h)
description: The ExGetSharedWaiterCount routine returns the number of waiters on shared access to a given resource.
old-location: kernel\exgetsharedwaitercount.htm
tech.root: kernel
ms.assetid: a9ca60a7-9bec-4c44-8803-85e183b48b01
ms.date: 04/30/2018
keywords: ["ExGetSharedWaiterCount function"]
ms.keywords: ExGetSharedWaiterCount, ExGetSharedWaiterCount routine [Kernel-Mode Driver Architecture], k102_af7dac19-3c9f-43d9-bcd3-c4a5e05ca8e5.xml, kernel.exgetsharedwaitercount, wdm/ExGetSharedWaiterCount
f1_keywords:
 - "wdm/ExGetSharedWaiterCount"
 - "ExGetSharedWaiterCount"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ExGetSharedWaiterCount
targetos: Windows
req.typenames: 
---

# ExGetSharedWaiterCount function


## -description


The <b>ExGetSharedWaiterCount</b> routine returns the number of waiters on shared access to a given resource. 


## -parameters




### -param Resource [in]

A pointer to the resource to be tested. 


## -returns



<b>ExGetSharedWaiterCount</b> returns the number of threads currently waiting to acquire the given resource for shared access. 




## -remarks



<b>ExGetSharedWaiterCount</b> can be called to get an estimate of how many other threads might be waiting to read the data protected by a particular resource variable. The caller cannot assume that the returned value remains constant for any particular interval.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetexclusivewaitercount">ExGetExclusiveWaiterCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>
 

 

