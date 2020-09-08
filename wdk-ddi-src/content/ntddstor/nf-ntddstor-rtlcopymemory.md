---
UID: NF:ntddstor.RtlCopyMemory
title: RtlCopyMemory macro (ntddstor.h)
description: The RtlCopyMemory routine copies the contents of a source memory block to a destination memory block.
tech.root: storage
ms.assetid: 0f83330e-b176-484e-a071-36a8ea4e00f8
ms.date: 09/20/2018
keywords: ["RtlCopyMemory macro"]
ms.keywords: RtlCopyMemory
req.header: ntddstor.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - RtlCopyMemory
 - ntddstor/RtlCopyMemory
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddstor.h
api_name:
 - RtlCopyMemory
---

# RtlCopyMemory macro (ntddstor.h)


## -description

The <b>RtlCopyMemory</b> routine copies the contents of a source memory block to a destination memory block.

## -parameters

### -param Destination

Datatype: void*. A pointer to the destination memory block to copy the bytes to.

### -param Source

Datatype: const void*. A pointer to the source memory block to copy the bytes from.

### -param Length

Datatype: size_t. The number of bytes to copy from the source to the destination.

## -remarks

<b>RtlCopyMemory</b> runs faster than <b>RtlMoveMemory</b>. However, <b>RtlCopyMemory</b> requires that the source memory block, which is defined by <i>Source</i> and <i>Length</i>, cannot overlap the destination memory block, which is defined by <i>Destination</i> and <i>Length</i>. In contrast, <b>RtlMoveMemory</b> correctly handles the case in which the source and destination memory blocks overlap.

New drivers should use the <b>RtlCopyMemory</b> routine instead of <b>RtlCopyBytes</b>.

Callers of <b>RtlCopyMemory</b> can be running at any IRQL if the source and destination memory blocks are in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlmovememory">RtlMoveMemory</a>

