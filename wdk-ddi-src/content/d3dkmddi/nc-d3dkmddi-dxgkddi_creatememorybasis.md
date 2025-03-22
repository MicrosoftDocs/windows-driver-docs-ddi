---
UID: NC:d3dkmddi.DXGKDDI_CREATEMEMORYBASIS
tech.root: display
title: DXGKDDI_CREATEMEMORYBASIS
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_CREATEMEMORYBASIS function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_CREATEMEMORYBASIS
f1_keywords:
 - DXGKDDI_CREATEMEMORYBASIS
 - d3dkmddi/DXGKDDI_CREATEMEMORYBASIS
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_CREATEMEMORYBASIS
---

# DXGKDDI_CREATEMEMORYBASIS function (d3dkmddi.h)

## -description

KMD's **DxgkDdiCreateMemoryBasis** function creates a handle for a collection of memory ranges that represent the allocation being operated on during dirty bit tracking.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgiDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in] A pointer to a [**DXGKARG_CREATEMEMORYBASIS**](ns-d3dkmddi-dxgkarg_creatememorybasis.md) structure that contains information for the basis being created.

## -returns

**DxgkDdiCreateMemoryBasis** returns a HANDLE to KMD's reference for tracking the collection of ranges. KMD should be able to transform this information into the information of the basis in subsequent commands like [**DxgkDdiDestroyMemoryBasis**](nc-d3dkmddi-dxgkddi_destroymemorybasis.md).

## -remarks

The tracking of modify operations on VRAM is for allocations that might not be backed contiguously. So the physical addresses represented in the tracking of dirty bits consists of a collection of ranges representing the allocation being operated on. **DxgkDdiCreateMemoryBasis** returns a handle to KMD's reference for tracking these ranges.

The KMD can rely on the following invariants:

* For each range in **Ranges**, both **SegmentOffset** and (**SegmentOffset** + **SizeInBytes** - 1) represent valid addresses on the segment referred to by **SegmentId**.

* All **Ranges** are pairwise disjoint; that is, the intersection between any two ranges is always null.

It is also common that **SegmentOffset** and **SizeInBytes** will respect certain page alignments when the created memory basis is used in certain dirty tracking DDIs. These values are described on those DDI's reference page, and are always a multiple of [**DXGK_DIRTY_BIT_TRACKING_SEGMENT_CAPS::PageSize**](ns-d3dkmddi-dxgk_dirty_bit_tracking_segment_caps.md).

*Dxgkrnl* otherwise doesn't make guarantees about the ordering of the addresses in the collection of **Ranges** or related assurances.

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DXGKARG_CREATEMEMORYBASIS**](ns-d3dkmddi-dxgkarg_creatememorybasis.md)

[**DxgkDdiDestroyMemoryBasis**](nc-d3dkmddi-dxgkddi_destroymemorybasis.md)
