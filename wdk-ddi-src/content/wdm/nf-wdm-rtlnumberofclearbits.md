---
UID: NF:wdm.RtlNumberOfClearBits
title: RtlNumberOfClearBits function (wdm.h)
description: The RtlNumberOfClearBits routine returns a count of the clear bits in a given bitmap variable.
old-location: kernel\rtlnumberofclearbits.htm
tech.root: kernel
ms.assetid: 739dc01d-7340-449f-8fe6-64e5c8284436
ms.date: 04/30/2018
ms.keywords: RtlNumberOfClearBits, RtlNumberOfClearBits routine [Kernel-Mode Driver Architecture], k109_1b655b45-806c-4199-91e6-2ed2f4d4e570.xml, kernel.rtlnumberofclearbits, wdm/RtlNumberOfClearBits
f1_keywords:
 - "wdm/RtlNumberOfClearBits"
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
req.irql: <= APC_LEVEL (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlNumberOfClearBits
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlNumberOfClearBits function


## -description


The <b>RtlNumberOfClearBits</b> routine returns a count of the clear bits in a given bitmap variable. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine. 


## -returns



<b>RtlNumberOfClearBits</b> returns the number of bits that are currently clear. 




## -remarks



Callers of <b>RtlNumberOfClearBits</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlNumberOfClearBits</b> can be called at any IRQL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbits">RtlFindClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearruns">RtlFindClearRuns</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindfirstrunclear">RtlFindFirstRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlongestrunclear">RtlFindLongestRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindnextforwardrunclear">RtlFindNextForwardRunClear</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofsetbits">RtlNumberOfSetBits</a>
 

 

