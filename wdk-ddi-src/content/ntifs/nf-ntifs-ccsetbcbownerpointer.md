---
UID: NF:ntifs.CcSetBcbOwnerPointer
title: CcSetBcbOwnerPointer function (ntifs.h)
description: The CcSetBcbOwnerPointer routine sets the owner thread pointer for a pinned buffer control block (BCB).
old-location: ifsk\ccsetbcbownerpointer.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcSetBcbOwnerPointer function"]
ms.keywords: CcSetBcbOwnerPointer, CcSetBcbOwnerPointer routine [Installable File System Drivers], ccref_9ad1d1a5-0600-4cfa-88d3-e4e5d2cd9df1.xml, ifsk.ccsetbcbownerpointer, ntifs/CcSetBcbOwnerPointer
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcSetBcbOwnerPointer
 - ntifs/CcSetBcbOwnerPointer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetBcbOwnerPointer
---

# CcSetBcbOwnerPointer function


## -description

The <b>CcSetBcbOwnerPointer</b> routine sets the owner thread pointer for a pinned buffer control block (BCB).

## -parameters

### -param Bcb [in]


Pointer to a pinned BCB structure that is owned by the current thread.

### -param OwnerPointer [in]


A valid resource owner pointer, which means a pointer to an allocated system address, with the low-order two bits set. This address may not be deallocated until after the BCB is unpinned by a subsequent call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindataforthread">CcUnpinDataForThread</a>.

## -remarks

File systems call <b>CcSetBcbOwnerPointer</b> to set the resource owner for a pinned buffer control block (BCB), in cases where another thread will unpin the BCB and thus the current thread can exit.

Each call to <b>CcSetBcbOwnerPointer</b> must be matched by a subsequent call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindataforthread">CcUnpinDataForThread</a>, which must be called with the same owner pointer.

BCBs that have been modified by <b>CcSetBcbOwnerPointer</b> cannot be unpinned by calling <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindata">CcUnpinData</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindata">CcUnpinData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindataforthread">CcUnpinDataForThread</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exsetresourceownerpointer">ExSetResourceOwnerPointer</a>
