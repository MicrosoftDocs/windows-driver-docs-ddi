---
UID: NF:wdm.RtlAreBitsSet
title: RtlAreBitsSet function (wdm.h)
description: The RtlAreBitsSet routine determines whether a given range of bits within a bitmap variable is set.
old-location: kernel\rtlarebitsset.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlAreBitsSet function"]
ms.keywords: RtlAreBitsSet, RtlAreBitsSet routine [Kernel-Mode Driver Architecture], k109_8d2248d2-13e9-4f90-8d09-a3ea51579da8.xml, kernel.rtlarebitsset, wdm/RtlAreBitsSet
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlAreBitsSet
 - wdm/RtlAreBitsSet
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlAreBitsSet
---

# RtlAreBitsSet function


## -description

The <b>RtlAreBitsSet</b> routine determines whether a given range of bits within a bitmap variable is set.

## -parameters

### -param BitMapHeader 

[in]
A pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine.

### -param StartingIndex 

[in]
Specifies the start of the bit range to be tested. This is a zero-based value indicating the position of the first bit in the range.

### -param Length 

[in]
Specifies how many bits to test.

## -returns

<b>RtlAreBitsSet</b> returns <b>TRUE</b> if <i>Length </i>consecutive bits beginning at <i>StartingIndex</i> are set (that is, all the bits from <i>StartingIndex </i>to (<i>StartingIndex </i>+ <i>Length</i>)). It returns <b>FALSE</b> if any bit in the given range is clear, if the given range is not a proper subset of the bitmap, or if the given <i>Length</i> is zero.

## -remarks

Callers of <b>RtlAreBitsSet</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlAreBitsSet</b> can be called at any IRQL.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear">RtlAreBitsClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcheckbit">RtlCheckBit</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbits">RtlFindSetBits</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlsetallbits">RtlSetAllBits</a>
