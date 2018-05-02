---
UID: NF:ntddk.KeGetCurrentProcessorNumber
title: KeGetCurrentProcessorNumber function
author: windows-driver-content
description: The KeGetCurrentProcessorNumber routine returns the system-assigned number of the current processor on which the caller is running.
old-location: kernel\kegetcurrentprocessornumber.htm
old-project: kernel
ms.assetid: 24de4374-fa73-4891-b212-6f5c7ed53407
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeGetCurrentProcessorNumber, KeGetCurrentProcessorNumber routine [Kernel-Mode Driver Architecture], k105_3faba96b-e6d9-40d2-a543-6ea95ce67c73.xml, kernel.kegetcurrentprocessornumber, ntddk/KeGetCurrentProcessorNumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	KeGetCurrentProcessorNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetCurrentProcessorNumber function


## -description


The <b>KeGetCurrentProcessorNumber</b> routine returns the system-assigned number of the current processor on which the caller is running.


## -parameters






## -returns



<b>KeGetCurrentProcessorNumber</b> returns a ULONG value that represents the processor on which the caller is currently running. 




## -remarks



<b>KeGetCurrentProcessorNumber</b> can be called to debug spin lock usage on SMP machines during driver development. A driver also might call <b>KeGetCurrentProcessorNumber</b> if it maintained some per-processor data and attempted to reduce cache-line contention.

The number of processors in an SMP machine is a zero-based value.

Windows 7 and later versions of Windows support processor groups. Drivers that are designed to handle information about processor groups should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552076">KeGetCurrentProcessorNumberEx</a> routine, which specifies a processor group, instead of <b>KeGetCurrentProcessorNumber</b>, which does not. However, the implementation of <b>KeGetCurrentProcessorNumber</b> in Windows 7 and later versions of Windows provides compatibility for drivers that were written for earlier versions of Windows. In this implementation, <b>KeGetCurrentProcessorNumber</b> returns the group-relative processor number if the caller is running on a processor in group 0, which is compatible with the behavior of this routine in earlier versions of Windows that do not support processor groups. If the caller is running on a processor in any group other than group 0, this routine returns a number that is less than the number of processors in group 0. This behavior ensures that the return value is less than the return value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552985">KeQueryActiveProcessorCount</a> routine.

If the call to <b>KeGetCurrentProcessorNumber</b> occurs at IRQL &lt;= APC_LEVEL, a processor switch can occur between instructions. Consequently, callers of <b>KeGetCurrentProcessorNumber</b> usually run at IRQL &gt;= DISPATCH_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552076">KeGetCurrentProcessorNumberEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552985">KeQueryActiveProcessorCount</a>
 

 

