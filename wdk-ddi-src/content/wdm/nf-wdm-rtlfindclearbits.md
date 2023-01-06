---
UID: NF:wdm.RtlFindClearBits
title: RtlFindClearBits function (wdm.h)
description: The RtlFindClearBits routine searches for a range of clear bits of a requested size within a bitmap.
tech.root: kernel
ms.date: 01/06/2023
keywords: ["RtlFindClearBits function"]
ms.keywords: RtlFindClearBits, RtlFindClearBits routine [Kernel-Mode Driver Architecture], k109_bf520772-12d8-403e-8b57-31a24e9a27b6.xml, kernel.rtlfindclearbits, wdm/RtlFindClearBits
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: IRQL <= APC_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlFindClearBits
 - wdm/RtlFindClearBits
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - RtlFindClearBits
---

## -description

The **RtlFindClearBits** routine searches for a range of clear bits of a requested size within a bitmap.

## -parameters

### -param BitMapHeader [in]

A pointer to the [RTL_BITMAP](/windows-hardware/drivers/kernel/eprocess) structure that describes the bitmap. This structure must have been initialized by the [RtlInitializeBitMap](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap) routine.

### -param NumberToFind [in]

Specifies how many contiguous clear bits will satisfy this request.

### -param HintIndex [in]

Specifies a zero-based bit position from which to start looking for a clear bit range of the given size.

## -returns

**RtlFindClearBits** either returns the zero-based starting bit index for a clear bit range of at least the requested size, or it returns 0xFFFFFFFF if it cannot find such a range within the given bitmap.

## -remarks

For a successful call, the returned bit position is not necessarily equivalent to the given *HintIndex*. If necessary, **RtlFindClearBits** searches the whole bitmap to locate a clear bit range of the requested size. Callers can find such a range more quickly when they can supply appropriate hints about where to start looking.

If a matching range is not found between the hint index and the end of the bitmap, **RtlFindClearBits** continues searching from the beginning of the bitmap back to the hint index.

If you only want an index returned that is greater than or equal to some value, use [**RtlFindNextForwardRunClear**](./nf-wdm-rtlfindnextforwardrunclear.md) instead.

Callers of **RtlFindClearBits** must be running at IRQL <= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at *BitMapHeader* is pageable. Otherwise, **RtlFindClearBits** can be called at any IRQL.

## -see-also

[RTL_BITMAP](/windows-hardware/drivers/kernel/eprocess)

[RtlAreBitsClear](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlarebitsclear)

[RtlFindClearBitsAndSet](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindclearbitsandset)

[RtlFindFirstRunClear](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindfirstrunclear)

[RtlFindLongestRunClear](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindlongestrunclear)

[RtlFindSetBits](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlfindsetbits)

[RtlInitializeBitMap](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlinitializebitmap)

[RtlNumberOfClearBits](/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlnumberofclearbits)
