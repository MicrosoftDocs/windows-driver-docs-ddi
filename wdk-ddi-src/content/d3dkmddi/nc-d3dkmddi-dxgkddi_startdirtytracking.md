---
UID: NC:d3dkmddi.DXGKDDI_STARTDIRTYTRACKING
tech.root: display
title: DXGKDDI_STARTDIRTYTRACKING
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_STARTDIRTYTRACKING function.
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
 - DXGKDDI_STARTDIRTYTRACKING
f1_keywords:
 - DXGKDDI_STARTDIRTYTRACKING
 - d3dkmddi/DXGKDDI_STARTDIRTYTRACKING
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_STARTDIRTYTRACKING
---

# DXGKDDI_STARTDIRTYTRACKING function (d3dkmddi.h)

## -description

KMD's **DxgkDdiStartDirtyTracking** function enables dirty bit tracking within the specified segment and given address range.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgiDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param hMemoryBasis

[in] Handle to the memory basis over which to start tracking dirty operations. KMD created this handle in a previous call to [**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md).

## -returns

**DxgkDdiStartDirtyTracking** returns STATUS_SUCCESS upon success. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

The driver only needs to ensure that dirty tracking is enabled for the specified memory basis. However, doing so at a coarser granularity (for example, enabling dirty tracking for the entire adapter or segment) is valid as long as all outstanding requests are honored.

*Dxgkrnl* might enable dirty page tracking on multiple segments or ranges within those segments simultaneously.

When dirty tracking is enabled, *Dxgkrnl* expects the dirty bitplane to be initialized to all zeroes (all pages unmodified).

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md)

[**DxgkDdiStopDirtyTracking**](nc-d3dkmddi-dxgkddi_stopdirtytracking.md)
