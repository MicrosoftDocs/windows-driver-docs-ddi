---
UID: NC:d3dkmddi.DXGKDDI_RESETENGINE
title: DXGKDDI_RESETENGINE (d3dkmddi.h)
description: Learn more about the DXGKDDI_RESETENGINE function.
ms.date: 10/02/2023
keywords: ["DXGKDDI_RESETENGINE callback function"]
ms.keywords: DXGKDDI_RESETENGINE, DXGKDDI_RESETENGINE callback, DxgkDdiResetEngine, DxgkDdiResetEngine callback function [Display Devices], d3dkmddi/DxgkDdiResetEngine, display.dxgkddiresetengine
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_RESETENGINE
 - d3dkmddi/DXGKDDI_RESETENGINE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKDDI_RESETENGINE
---

# DXGKDDI_RESETENGINE callback function

## -description

The display port driver's GPU scheduler calls the miniport driver's (KMD's) **DxgkDdiResetEngine** function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.

## -parameters

### -param hAdapter

[in] A handle to a context block that is associated with a display adapter. The KMD previously provided this handle to *Dxgkrnl* in the **MiniportDeviceContext** output parameter of the [**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md) function.

### -param pResetEngine

[in/out] A [**DXGKARG_RESETENGINE**](ns-d3dkmddi-_dxgkarg_resetengine.md) structure that specifies the node to be reset and supplies a fence identifier for the last aborted packet.

## -returns

**DxgkDdiResetEngine** returns STATUS_SUCCESS if the function succeeds. Otherwise, this function returns one of the error codes defined in *Ntstatus.h*.

## -remarks

The KMD should return from a call to this function only when all of the following criteria are met:

* The reset operation is completed.
* Nothing remains in the physical adapter's hardware queue.
* The specified nodes are ready to accept new packets.

This function should be made pageable.

The operating system guarantees that this function follows the [first level synchronization mode](/windows-hardware/drivers/display/threading-and-synchronization-first-level).

For more information, see [TDR changes in Windows 8](/windows-hardware/drivers/display/tdr-changes-in-windows-8).

## -see-also

[**DXGKARG_RESETENGINE**](ns-d3dkmddi-_dxgkarg_resetengine.md)

[**DxgkDdiAddDevice**](../dispmprt/nc-dispmprt-dxgkddi_add_device.md)
