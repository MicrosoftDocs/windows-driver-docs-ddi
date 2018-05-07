---
UID: NF:wdm.ExGetExclusiveWaiterCount
title: ExGetExclusiveWaiterCount function
author: windows-driver-content
description: The ExGetExclusiveWaiterCount routine returns the number of waiters on exclusive access to a given resource.
old-location: kernel\exgetexclusivewaitercount.htm
old-project: kernel
ms.assetid: 032989b7-ba61-4cb3-b6b5-ac66124cdd79
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ExGetExclusiveWaiterCount, ExGetExclusiveWaiterCount routine [Kernel-Mode Driver Architecture], k102_bd65d9e8-06bf-4492-88f1-bfd4e46fb29e.xml, kernel.exgetexclusivewaitercount, wdm/ExGetExclusiveWaiterCount
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExGetExclusiveWaiterCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExGetExclusiveWaiterCount function


## -description


The <b>ExGetExclusiveWaiterCount</b> routine returns the number of waiters on exclusive access to a given resource.


## -parameters




### -param Resource [in]

A pointer to the resource to be tested.


## -returns



<b>ExGetExclusiveWaiterCount</b> returns the number of threads currently waiting to acquire the given resource for exclusive access.




## -remarks



<b>ExGetExclusiveWaiterCount</b> can be called to get an estimate of how many other threads might be waiting to modify the data protected by a particular resource variable. The caller cannot assume that the returned value remains constant for any particular interval.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544351">ExAcquireResourceExclusiveLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544363">ExAcquireResourceSharedLite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544367">ExAcquireSharedStarveExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544370">ExAcquireSharedWaitForExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545290">ExGetSharedWaiterCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545585">ExReleaseResourceForThreadLite</a>
 

 

