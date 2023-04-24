---
UID: NF:ndis.NdisMoveMemory
title: NdisMoveMemory macro (ndis.h)
description: The NdisMoveMemory function copies a specified number of bytes from one caller-supplied location to another.
old-location: netvista\ndismovememory.htm
tech.root: netvista
ms.date: 11/24/2022
keywords: ["NdisMoveMemory macro"]
ms.keywords: NdisMoveMemory, NdisMoveMemory macro [Network Drivers Starting with Windows Vista], ndis/NdisMoveMemory, ndis_memory_ref_19f420d5-3747-48fa-a6c6-d1088449075b.xml, netvista.ndismovememory
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlCopyMemory (not RtlMoveMemory) instead.
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
req.irql: See Remarks section
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisMoveMemory
 - ndis/NdisMoveMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NdisMoveMemory
---

# NdisMoveMemory macro


## -description

The **NdisMoveMemory** function copies a specified number of bytes from one caller-supplied location to another.

## -parameters

### -param Destination [out]


A pointer to a system-space buffer that is the destination of the move. This buffer must be at
least **Length** bytes in size.

### -param Source [in]


A pointer to a system-space buffer from which this function copies the data to the destination buffer. This buffer must be at least **Length** bytes in size.

### -param Length [in]


The number of bytes to copy.

## -remarks

Both **Source** and Destination are virtual addresses.

If either address falls within a range of device memory that was mapped with [**NdisMMapIoSpace**](nf-ndis-ndismmapiospace.md), a miniport driver should call one of the **Ndis..MappedMemory** functions instead of **NdisMoveMemory**.

The range specified by **Source** and **Length** cannot overlap the **Destination** range.

Callers of **NdisMoveMemory** can run at any IRQL if the given **Source** and **Destination** are resident. Otherwise, callers must be running at IRQL < DISPATCH_LEVEL, as, for example if either address is on the stack.

## -see-also

[**NdisAllocateMemoryWithTagPriority**](nf-ndis-ndisallocatememorywithtagpriority.md)

[**NdisMMapIoSpace**](nf-ndis-ndismmapiospace.md)
