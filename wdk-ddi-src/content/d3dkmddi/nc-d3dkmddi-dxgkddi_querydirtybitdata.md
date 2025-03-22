---
UID: NC:d3dkmddi.DXGKDDI_QUERYDIRTYBITDATA
tech.root: display
title: DXGKDDI_QUERYDIRTYBITDATA
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_QUERYDIRTYBITDATA function.
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
 - DXGKDDI_QUERYDIRTYBITDATA
f1_keywords:
 - DXGKDDI_QUERYDIRTYBITDATA
 - d3dkmddi/DXGKDDI_QUERYDIRTYBITDATA
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_QUERYDIRTYBITDATA
---

# DXGKDDI_QUERYDIRTYBITDATA function (d3dkmddi.h)

## -description

*Dxgkrnl* calls **DxgkDdiQueryDirtyBitData** to request a copy of the dirty bitplane data from the kernel-mode display miniport driver (KMD).

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgiDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pArgs

[in/out] A pointer to a [**DXGKARG_QUERYDIRTYBITDATA**](ns-d3dkmddi-dxgkarg_querydirtybitdata.md) structure that contains input and output information for the query.

## -returns

**DxgkDdiQueryDirtyBitData** returns STATUS_SUCCESS if the query was successfully. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

The function provides the memory basis and potential subrange identifiers for the requested dirty information. KMD must write the resulting data to the output buffer. **DxgkDdiQueryDirtyBitData** allows either querying all ranges of the memory basis or a single one.

When memory is readily available, *Dxgkrnl* will try to accelerate this operation using a single call to query all needed data at once. However, under low memory conditions, forward progress using a smaller fixed sized buffer might be required, which is only a smaller subset of the memory basis being tracked from a prior call to DdiStartDirtyTracking. The requested dirty bitplane range will never exceed an actively tracked dirty range.

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DXGKARG_QUERYDIRTYBITDATA**](ns-d3dkmddi-dxgkarg_querydirtybitdata.md)
