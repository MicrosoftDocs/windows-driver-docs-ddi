---
UID: NF:ntddk.KeQueryMaximumProcessorCountEx
title: KeQueryMaximumProcessorCountEx function (ntddk.h)
description: The KeQueryMaximumProcessorCountEx routine returns the maximum number of logical processors in a specified group in a multiprocessor system.
old-location: kernel\kequerymaximumprocessorcountex.htm
tech.root: kernel
ms.assetid: 6ccc0f8c-d7b7-4043-8580-d35345d884cc
ms.date: 04/30/2018
ms.keywords: KeQueryMaximumProcessorCountEx, KeQueryMaximumProcessorCountEx routine [Kernel-Mode Driver Architecture], k105_594dbccc-80ed-4d33-a8ed-a6df6bfdfc09.xml, kernel.kequerymaximumprocessorcountex, wdm/KeQueryMaximumProcessorCountEx
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeQueryMaximumProcessorCountEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeQueryMaximumProcessorCountEx function


## -description


The <b>KeQueryMaximumProcessorCountEx</b> routine returns the maximum number of logical processors in a specified group in a multiprocessor system.


## -parameters




### -param GroupNumber [in]

Specifies a group number. If a multiprocessor system contains <i>n</i> groups, the groups are numbered from 0 to <i>n</i>-1. To obtain the maximum number of processors in the system, set this parameter to ALL_PROCESSOR_GROUPS, which is defined in the Winnt.h and Ntdef.h header files.


## -returns



<b>KeQueryMaximumProcessorCountEx</b> returns the maximum number of logical processors in the specified group or in the system, as indicated by the value of the <i>GroupNumber</i> parameter.




## -remarks



The value that is returned by <b>KeQueryMaximumProcessorCountEx</b> remains constant during runtime. This value depends on the hardware configuration of the multiprocessor system, but it can never exceed a fixed limit that is set by the Windows operating system. This limit is 32 logical processors for 32-bit versions of Windows and 64 logical processors for 64-bit versions of Windows.

In contrast, the value that is returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a> routine can change during runtime as processors are dynamically added to the system.

A related routine, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553042">KeQueryMaximumProcessorCount</a>, returns a maximum processor count, but this routine, unlike <b>KeQueryMaximumProcessorCountEx</b>, does not accept a group number as an input parameter. In Windows 7 and later versions of the Windows operating system, <b>KeQueryMaximumProcessorCount</b> returns the maximum number of logical processors in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support groups. This behavior ensures that existing drivers that call <b>KeQueryMaximumProcessorCount</b> and that use no group-oriented features will run correctly in multiprocessor systems that have two or more groups. However, drivers that use any group-oriented features in Windows 7 and later versions of the Windows operating system should call <b>KeQueryMaximumProcessorCountEx</b> instead of <b>KeQueryMaximumProcessorCount</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553042">KeQueryMaximumProcessorCount</a>
 

 

