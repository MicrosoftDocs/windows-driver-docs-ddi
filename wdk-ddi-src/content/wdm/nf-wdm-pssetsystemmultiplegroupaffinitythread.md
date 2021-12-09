---
UID: NF:wdm.PsSetSystemMultipleGroupAffinityThread
tech.root: kernel
title: PsSetSystemMultipleGroupAffinityThread
ms.date: 06/03/2021
targetos: Windows
description: The PsSetSystemMultipleGroupAffinityThread function sets the multi-group system affinity of the current thread.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - PsSetSystemMultipleGroupAffinityThread
f1_keywords:
 - PsSetSystemMultipleGroupAffinityThread
 - wdm/PsSetSystemMultipleGroupAffinityThread
dev_langs:
 - c++
---

## -description

The **PsSetSystemMultipleGroupAffinityThread** function sets the multi-group system affinity of the current thread.

## -parameters

### -param GroupAffinities [in]


Supplies a pointer to an array of group affinity structures, which describe the new system affinity of the current thread.

### -param GroupCount [in]


Supplies the number of elements in the group affinity array.

### -param AffinityToken [in, out]


Supplies a pointer to an affinity token structure which must be returned by [**PsAllocateAffinityToken**](nf-wdm-psallocateaffinitytoken.md). On output it receives an opaque affinity token that must be passed to [**PsRevertToUserMultipleGroupAffinity**](nf-wdm-psreverttousermultiplegroupaffinitythread.md) to revert the thread to its previous affinity.

## -returns

Returns an NTSTATUS code.

## -remarks

## -see-also

[PsAllocateAffinityToken](nf-wdm-psallocateaffinitytoken.md)

[PsRevertToUserMultipleGroupAffinity](nf-wdm-psreverttousermultiplegroupaffinitythread.md)
