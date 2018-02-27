---
UID: NF:wdm.KeGetProcessorIndexFromNumber
title: KeGetProcessorIndexFromNumber function
author: windows-driver-content
description: The KeGetProcessorIndexFromNumber routine converts a group number and a group-relative processor number to a systemwide processor index.
old-location: kernel\kegetprocessorindexfromnumber.htm
old-project: kernel
ms.assetid: c7d8ca52-a1e1-4f5f-9ffe-d64cec47eac7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeGetProcessorIndexFromNumber, KeGetProcessorIndexFromNumber routine [Kernel-Mode Driver Architecture], k105_57b362f6-81dc-4630-a940-0d91577bf886.xml, kernel.kegetprocessorindexfromnumber, wdm/KeGetProcessorIndexFromNumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
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
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeGetProcessorIndexFromNumber function


## -description


The <b>KeGetProcessorIndexFromNumber</b> routine converts a group number and a group-relative processor number to a systemwide processor index.


## -syntax


````
ULONG KeGetProcessorIndexFromNumber(
  _In_ PPROCESSOR_NUMBER ProcNumber
);
````


## -parameters




### -param ProcNumber [in]

A pointer to a caller-allocated <a href="..\minitape\ns-minitape-_processor_number.md">PROCESSOR_NUMBER</a> structure that contains a group number and a group-relative processor number.


## -returns



<b>KeGetProcessorIndexFromNumber</b> returns a systemwide processor index if the call is successful. If <i>ProcNumber</i> points to an invalid <b>PROCESSOR_NUMBER</b> value, the routine returns INVALID_PROCESSOR_INDEX, which is defined in the Wdm.h header file. 




## -remarks



This routine accepts as input a <b>PROCESSOR_NUMBER</b> structure that identifies a processor by its group number and its processor number within the group. The return value is a processor index that identifies the processor across the entire multiprocessor system.

For example, if a multiprocessor system contains two groups, and each group contains 64 logical processors, the processor numbers in each group range from 0 to 63, but the systemwide processor indexes range from 0 to 127.

To obtain the total number of active logical processors in the system, call the <a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a> routine and set this routine's <i>GroupNumber</i> parameter to ALL_PROCESSOR_GROUPS.

The <a href="..\wdm\nf-wdm-kegetprocessornumberfromindex.md">KeGetProcessorNumberFromIndex</a> routine converts a systemwide processor index to a group number and a group-relative processor number.




## -see-also

<a href="..\minitape\ns-minitape-_processor_number.md">PROCESSOR_NUMBER</a>



<a href="..\wdm\nf-wdm-kegetprocessornumberfromindex.md">KeGetProcessorNumberFromIndex</a>



<a href="..\wdm\nf-wdm-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeGetProcessorIndexFromNumber routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

