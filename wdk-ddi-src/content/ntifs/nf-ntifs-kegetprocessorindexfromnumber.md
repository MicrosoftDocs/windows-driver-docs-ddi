---
UID: NF:ntifs.KeGetProcessorIndexFromNumber
title: KeGetProcessorIndexFromNumber function
author: windows-driver-content
description: The KeGetProcessorIndexFromNumber routine converts a group number and a group-relative processor number to a systemwide processor index.
old-location: kernel\kegetprocessorindexfromnumber.htm
tech.root: kernel
ms.assetid: c7d8ca52-a1e1-4f5f-9ffe-d64cec47eac7
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeGetProcessorIndexFromNumber, KeGetProcessorIndexFromNumber routine [Kernel-Mode Driver Architecture], k105_57b362f6-81dc-4630-a940-0d91577bf886.xml, kernel.kegetprocessorindexfromnumber, wdm/KeGetProcessorIndexFromNumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeGetProcessorIndexFromNumber
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeGetProcessorIndexFromNumber function


## -description


The <b>KeGetProcessorIndexFromNumber</b> routine converts a group number and a group-relative processor number to a systemwide processor index.


## -parameters




### -param ProcNumber [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff559913">PROCESSOR_NUMBER</a> structure that contains a group number and a group-relative processor number.


## -returns



<b>KeGetProcessorIndexFromNumber</b> returns a systemwide processor index if the call is successful. If <i>ProcNumber</i> points to an invalid <b>PROCESSOR_NUMBER</b> value, the routine returns INVALID_PROCESSOR_INDEX, which is defined in the Wdm.h header file. 




## -remarks



This routine accepts as input a <b>PROCESSOR_NUMBER</b> structure that identifies a processor by its group number and its processor number within the group. The return value is a processor index that identifies the processor across the entire multiprocessor system.

For example, if a multiprocessor system contains two groups, and each group contains 64 logical processors, the processor numbers in each group range from 0 to 63, but the systemwide processor indexes range from 0 to 127.

To obtain the total number of active logical processors in the system, call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a> routine and set this routine's <i>GroupNumber</i> parameter to ALL_PROCESSOR_GROUPS.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552100">KeGetProcessorNumberFromIndex</a> routine converts a systemwide processor index to a group number and a group-relative processor number.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552100">KeGetProcessorNumberFromIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559913">PROCESSOR_NUMBER</a>
 

 

