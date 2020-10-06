---
UID: NC:d3dkmddi.DXGKDDI_RESETENGINE
title: DXGKDDI_RESETENGINE (d3dkmddi.h)
description: The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.
old-location: display\dxgkddiresetengine.htm
ms.assetid: 9c2097b2-5742-422c-a650-7efff2484970
ms.date: 05/10/2018
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
 - DxgkDdiResetEngine
product:
 - Windows
---

# DXGKDDI_RESETENGINE callback function


## -description

The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.

## -parameters

### -param hAdapter

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.

### -param pResetEngine

A value of type  <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_resetengine">DXGKARG_RESETENGINE</a> that specifies nodes that are to be reset and supplies a fence identifier for the last aborted packet.

## -returns

Returns <b>STATUS_SUCCESS</b> if the function succeeds. Otherwise, this function returns one of the error codes defined in Ntstatus.h.

## -remarks

The display miniport driver should return from a call to this function only when the reset operation is completed, nothing remains in the physical adapter's hardware queue, and the specified nodes are ready to accept new packets.

 This function should be made pageable.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="/windows-hardware/drivers/display/threading-and-synchronization-first-level">Threading and Synchronization First Level</a>.

For more information, see  <a href="/windows-hardware/drivers/display/tdr-changes-in-windows-8">TDR changes in Windows 8</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_resetengine">DXGKARG_RESETENGINE</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>