---
UID: NF:wdm.RtlFindSetBitsAndClear
title: RtlFindSetBitsAndClear function (wdm.h)
description: The RtlFindSetBitsAndClear routine searches for a range of set bits of a requested size within a bitmap and clears all bits in the range when it has been located.
old-location: kernel\rtlfindsetbitsandclear.htm
tech.root: kernel
ms.assetid: d88797c6-c06c-4c3b-a3e4-baf412e051ef
ms.date: 04/30/2018
ms.keywords: RtlFindSetBitsAndClear, RtlFindSetBitsAndClear routine [Kernel-Mode Driver Architecture], k109_a6043f35-d317-434a-93c1-1c44aa9e8cd4.xml, kernel.rtlfindsetbitsandclear, wdm/RtlFindSetBitsAndClear
ms.topic: function
f1_keywords:
 - "wdm/RtlFindSetBitsAndClear"
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
- RtlFindSetBitsAndClear
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlFindSetBitsAndClear function


## -description


The <b>RtlFindSetBitsAndClear</b> routine searches for a range of set bits of a requested size within a bitmap and clears all bits in the range when it has been located. 


## -parameters




### -param BitMapHeader [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine. 


### -param NumberToFind [in]

Specifies how many contiguous set bits will satisfy this request. 


### -param HintIndex [in]

Specifies a zero-based bit position around which to start looking for a set bit range of the given size. 


## -returns



<b>RtlFindSetBitsAndClear</b> either returns the zero-based starting bit index for a set bit range of the requested size that it cleared, or it returns 0xFFFFFFFF if it cannot find such a range within the given bitmap variable. 




## -remarks



For a successful call, the returned bit position is not necessarily equivalent to the given <i>HintIndex</i>. If necessary, <b>RtlFindSetBitsAndClear</b> searches the whole bitmap to locate a set bit range of the requested size. However, it starts searching for the requested range near <i>HintIndex</i>, so callers can clear such a range more quickly when they can supply appropriate hints about where to start looking.

Callers of <b>RtlFindSetBitsAndClear</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindSetBitsAndClear</b> can be called at any IRQL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsset">RtlAreBitsSet</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlclearallbits">RtlClearAllBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlclearbits">RtlClearBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbits">RtlFindSetBits</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofsetbits">RtlNumberOfSetBits</a>
 

 

