---
UID: NC:d3dkmddi.DXGKDDI_STOPDIRTYTRACKING
tech.root: display
title: DXGKDDI_STOPDIRTYTRACKING
ms.date: 03/28/2024
targetos: Windows
description: Learn more about the DXGKDDI_STOPDIRTYTRACKING function.
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
 - DXGKDDI_STOPDIRTYTRACKING
f1_keywords:
 - DXGKDDI_STOPDIRTYTRACKING
 - d3dkmddi/DXGKDDI_STOPDIRTYTRACKING
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_STOPDIRTYTRACKING
---

# DXGKDDI_STOPDIRTYTRACKING function (d3dkmddi.h)

## -description

KMD's **DxgkDdiStopDirtyTracking** function disables dirty bit tracking within the specified segment and given address range.

## -parameters

### -param hAdapter

[in] A handle to a context block associated with a display adapter. KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgiDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param hMemoryBasis

[in] Handle to the memory basis over which to stop tracking dirty operations. KMD created this handle in a previous call to [**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md).

## -returns

**DxgkDdiStopDirtyTracking** returns STATUS_SUCCESS upon success. Otherwise, it returns an appropriate NTSTATUS code.

## -remarks

The driver should ensure that all previous start requests are still honored. For example, if KMD only supports dirty tracking on the entire segment at once and there are two outstanding requests for dirty tracking, stopping only one request should keep dirty bit tracking enabled for the other request.

The driver can be guaranteed that a call to **DxgkDdiStopDirtyTracking** will specify the same ranges of memory as the corresponding [**DxgkDdiStartDirtyTracking**](nc-d3dkmddi-dxgkddi_startdirtytracking.md) calls. For example, if *Dxgkrnl* made a call to start dirty tracking on [0, 1GB) of segment 1, there will eventually be a resulting call to stop dirty tracking on the segment [0, 1GB) range in segment 1.

For more information, see [Dirty bit tracking](/windows-hardware/drivers/display/dirty-bit-tracking).

## -see-also

[**DxgkDdiCreateMemoryBasis**](nc-d3dkmddi-dxgkddi_creatememorybasis.md)

[**DxgkDdiStartDirtyTracking**](nc-d3dkmddi-dxgkddi_startdirtytracking.md)
