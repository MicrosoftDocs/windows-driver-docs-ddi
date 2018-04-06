---
UID: NS:miniport._PROCESSOR_NUMBER
title: "_PROCESSOR_NUMBER"
author: windows-driver-content
description: The PROCESSOR_NUMBER structure identifies a processor by its group number and group-relative processor number.
old-location: kernel\processor_number.htm
old-project: kernel
ms.assetid: 6ceb8d0f-8c26-4487-a976-ac92e2aca5e0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPROCESSOR_NUMBER, PPROCESSOR_NUMBER, PPROCESSOR_NUMBER structure pointer [Kernel-Mode Driver Architecture], PROCESSOR_NUMBER, PROCESSOR_NUMBER structure [Kernel-Mode Driver Architecture], _PROCESSOR_NUMBER, kernel.processor_number, kstruct_c_d3a9199a-f6d3-4d2d-877a-6e856e80ebb9.xml, miniport/PPROCESSOR_NUMBER, miniport/PROCESSOR_NUMBER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: miniport.h
req.include-header: Windows.h, Ntdef.h, Wdm.h, Ntddk.h, Winnt.h, Minitape.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 7 and later versions of the Windows operating system.
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
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	miniport.h
api_name:
-	PROCESSOR_NUMBER
product:
- Windows
targetos: Windows
req.typenames: PROCESSOR_NUMBER, *PPROCESSOR_NUMBER
---

# _PROCESSOR_NUMBER structure


## -description


The <b>PROCESSOR_NUMBER</b> structure identifies a processor by its group number and group-relative processor number.


## -struct-fields




### -field Group

The group number. If multiprocessor system contains <i>n</i> groups, the groups are numbered from 0 to <i>n</i>-1. 


### -field Number

The group-relative processor number. If a group contains <i>m</i> logical processors, the processors are numbered from 0 to <i>m</i>-1. 


### -field Reserved

Reserved for future use. Initialize to zero. 


## -remarks



Windows 7 is the first version of Windows to support processor groups. In Windows 7, only 64-bit versions of Windows support multiple groups; 32-bit versions of Windows support only one group. If a multiprocessor system is running a 64-bit version of Windows and contains no more than 64 logical processors, Windows assigns all processors to group 0. A multiprocessor system that is running a 32-bit version of Windows can contain no more than 32 processors.

In Windows 7, the maximum number of groups in a multiprocessor system is four, but this value might change in future versions of Windows. The safest way to determine the maximum number of groups in Windows 7 or a later version of Windows is to call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553035">KeQueryMaximumGroupCount</a> routine. Kernel-mode drivers that call <b>KeQueryMaximumGroupCount</b> will not require code changes if the formula that is used to calculate the maximum number of groups changes in a future version of Windows.

Kernel-mode routines that use the <b>PROCESSOR_NUMBER</b> structure include <a href="https://msdn.microsoft.com/library/windows/hardware/ff552076">KeGetCurrentProcessorNumberEx</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff552096">KeGetProcessorIndexFromNumber</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff552100">KeGetProcessorNumberFromIndex</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff553031">KeQueryLogicalProcessorRelationship</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552076">KeGetCurrentProcessorNumberEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552096">KeGetProcessorIndexFromNumber</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552100">KeGetProcessorNumberFromIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553031">KeQueryLogicalProcessorRelationship</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553035">KeQueryMaximumGroupCount</a>
 

 

