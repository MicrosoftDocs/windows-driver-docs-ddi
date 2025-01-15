---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_UPDATE_STATE
tech.root: display
title: DXGKDDI_DISPLAYMUX_UPDATE_STATE
ms.date: 01/13/2025
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_UPDATE_STATE function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
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
 - dispmprt.h
api_name:
 - DXGKDDI_DISPLAYMUX_UPDATE_STATE
f1_keywords:
 - DXGKDDI_DISPLAYMUX_UPDATE_STATE
 - dispmprt/DXGKDDI_DISPLAYMUX_UPDATE_STATE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_UPDATE_STATE
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxUpdateState** function to notify the driver of the current mux state.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param MuxSwitchedToTarget

[in] A Boolean value that indicates whether the mux is currently switched to connect the specified **VidPnTargetId** to the panel.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

*Dxgkrnl* calls **DxgkDdiDisplayMuxUpdateState** to provide the driver with the current mux state in the following cases:

* At driver start, which allows the driver to avoid timely polling sequences when the panel isn't connected.
* On return from sleep (to D0 power state from D*x*). When returning from some power states (for example, hibernate) the firmware might have to reset the mux and hence the driver doesn't know the state.

**DxgkDdiDisplayMuxUpdateState** is called before any display-related DDIs involving the target that the mux is connected to.

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).
