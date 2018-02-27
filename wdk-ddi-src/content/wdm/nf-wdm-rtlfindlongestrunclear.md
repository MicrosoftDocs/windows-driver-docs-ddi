---
UID: NF:wdm.RtlFindLongestRunClear
title: RtlFindLongestRunClear function
author: windows-driver-content
description: The RtlFindLongestRunClear routine searches for the largest contiguous range of clear bits within a given bitmap.
old-location: kernel\rtlfindlongestrunclear.htm
old-project: kernel
ms.assetid: 6d68cb0f-d0b8-4468-8def-60a65780480e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlFindLongestRunClear, RtlFindLongestRunClear routine [Kernel-Mode Driver Architecture], k109_a6295996-9e2c-4d19-9ee9-1dc7802bd145.xml, kernel.rtlfindlongestrunclear, wdm/RtlFindLongestRunClear
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlFindLongestRunClear
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlFindLongestRunClear function


## -description


The <b>RtlFindLongestRunClear</b> routine searches for the largest contiguous range of clear bits within a given bitmap. 


## -syntax


````
ULONG RtlFindLongestRunClear(
  _In_  PRTL_BITMAP BitMapHeader,
  _Out_ PULONG      StartingIndex
);
````


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param StartingIndex [out]

Pointer to a variable in which the starting index of the longest clear run in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the returned range. 


## -returns



<b>RtlFindLongestRunClear</b> returns either the number of bits in the run beginning at <i>StartingIndex</i>, or zero if it cannot find a run of clear bits within the bitmap. 




## -remarks



A returned run can have a single clear bit.

Callers of <b>RtlFindLongestRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindLongestRunClear</b> can be called at any IRQL.




## -see-also

<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>



<a href="..\wdm\nf-wdm-rtlfindnextforwardrunclear.md">RtlFindNextForwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>



<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



<a href="..\wdm\nf-wdm-rtlnumberofclearbits.md">RtlNumberOfClearBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlsetbits.md">RtlSetBits</a>



<a href="..\wdm\nf-wdm-rtlfindclearruns.md">RtlFindClearRuns</a>



<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindLongestRunClear routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

