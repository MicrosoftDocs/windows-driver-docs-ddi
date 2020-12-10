---
UID: NF:wdm.RtlClearAllBits
title: RtlClearAllBits function (wdm.h)
description: The RtlClearAllBits routine sets all bits in a given bitmap variable to zero.
old-location: kernel\rtlclearallbits.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["RtlClearAllBits function"]
ms.keywords: RtlClearAllBits, RtlClearAllBits routine [Kernel-Mode Driver Architecture], k109_6fb17a55-6839-411c-9289-720657ba4983.xml, kernel.rtlclearallbits, wdm/RtlClearAllBits
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: <= APC_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlClearAllBits
 - wdm/RtlClearAllBits
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
 - Ntdll.dll
api_name:
 - RtlClearAllBits
---

# RtlClearAllBits function


## -description

The <b>RtlClearAllBits</b> routine sets all bits in a given bitmap variable to zero.

## -parameters

### -param BitMapHeader 

[in]
A pointer to the <a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a> routine.

## -returns

None

## -remarks

Callers of <b>RtlClearAllBits</b> must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearAllBits</b> can be called at any IRQL.

## -see-also

<a href="/windows-hardware/drivers/kernel/eprocess">RTL_BITMAP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear">RtlAreBitsClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsset">RtlAreBitsSet</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlclearbits">RtlClearBits</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbits">RtlFindSetBits</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbitsandclear">RtlFindSetBitsAndClear</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap">RtlInitializeBitMap</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofsetbits">RtlNumberOfSetBits</a>
