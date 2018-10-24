---
UID: NF:ntddk.KeQueryActiveProcessorCount
title: KeQueryActiveProcessorCount function
author: windows-driver-content
description: The KeQueryActiveProcessorCount routine returns the number of currently active processors.
old-location: kernel\kequeryactiveprocessorcount.htm
tech.root: kernel
ms.assetid: 4369ad33-ba4a-45db-9a41-e77d6c55da53
ms.date: 04/30/2018
ms.keywords: KeQueryActiveProcessorCount, KeQueryActiveProcessorCount routine [Kernel-Mode Driver Architecture], k105_23574ace-ab66-43bb-976f-ca7310cece9a.xml, kernel.kequeryactiveprocessorcount, wdm/KeQueryActiveProcessorCount
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeQueryActiveProcessorCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryActiveProcessorCount function


## -description


The <b>KeQueryActiveProcessorCount</b> routine returns the number of currently active processors.


## -parameters




### -param ActiveProcessors [out, optional]

A pointer to a [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity)-typed variable into which the routine writes a bitmask that represents the set of currently active processors. In a hot-add environment, this mask may change during runtime. This parameter is optional and can be specified as <b>NULL</b> if the caller does not require the mask of active processors. 


## -returns



<b>KeQueryActiveProcessorCount</b> returns the number of currently active processors. 




## -remarks



A device driver calls the <b>KeQueryActiveProcessorCount</b> routine to retrieve the number of currently active processors. Device drivers that are built for Windows Vista and later versions of the Windows operating system should not use the <b>KeNumberProcessors</b> kernel variable for this purpose.

Callers cannot assume that the <b>KeQueryActiveProcessorCount</b> routine maps processors to bits in the returned [**KAFFINITY**](https://docs.microsoft.com/windows-hardware/drivers/kernel/interrupt-affinity-and-priority#about-kaffinity) value consecutively, or that the routine will return the same bitmask each time it is called.

Callers must also be aware that the value returned by <b>KeQueryActiveProcessorCount</b> can change at runtime on versions of Windows that support hot-add CPU functionality.

If necessary, register for notification of changes to the number of processors by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a> routine.

To query just the affinity mask without getting the number of active processors, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553001">KeQueryActiveProcessors</a>.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a> routine, which specifies a processor group, instead of <b>KeQueryActiveProcessorCount</b>, which does not. However, the implementation of <b>KeQueryActiveProcessorCount</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows, which do not support processor groups. In this implementation, <b>KeQueryActiveProcessorCount</b> returns the number of active logical processors in group 0, and writes an affinity mask to *<i>ActiveProcessors</i> that specifies the set of active logical processors in group 0. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553001">KeQueryActiveProcessors</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553120">KeRegisterProcessorChangeCallback</a>
 

 

