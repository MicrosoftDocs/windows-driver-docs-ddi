---
UID: NC:d3dkmddi.DXGKDDISETPOWERCOMPONENTFSTATE
title: DXGKDDISETPOWERCOMPONENTFSTATE (d3dkmddi.h)
description: Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state).
old-location: display\dxgkddisetpowercomponentfstate.htm
ms.assetid: C68CC6F1-83D6-43D9-93F3-99E3A990C7D7
ms.date: 05/10/2018
keywords: ["DXGKDDISETPOWERCOMPONENTFSTATE callback function"]
ms.keywords: DXGKDDISETPOWERCOMPONENTFSTATE, DXGKDDISETPOWERCOMPONENTFSTATE callback, DxgkDdiSetPowerComponentFState, DxgkDdiSetPowerComponentFState callback function [Display Devices], d3dkmddi/DxgkDdiSetPowerComponentFState, display.dxgkddisetpowercomponentfstate
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDISETPOWERCOMPONENTFSTATE
 - d3dkmddi/DXGKDDISETPOWERCOMPONENTFSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkDdiSetPowerComponentFState
product:
 - Windows
---

# DXGKDDISETPOWERCOMPONENTFSTATE callback function


## -description

Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state).

## -parameters

### -param DriverContext

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

### -param ComponentIndex

The power component index specified by  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

### -param FState

An F-state value that the display miniport driver has reported to the DirectX graphics kernel subsystem.

## -returns

      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns STATUS_INVALID_PARAMETER.

## -remarks

The operating system calls <i>DxgkDdiSetPowerComponentFState</i> only if the display miniport driver indicates support by setting <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>.<b>SupportRuntimePowerManagement</b> to <b>TRUE</b>.

<div class="alert"><b>Note</b>  To avoid a possible deadlock, do not call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentactive">DxgkCbSetPowerComponentActive</a> function until this function has returned.</div>
<div> </div>
When the display miniport driver transitions a power component from the F0 (fully on) state to another F-state, it should save the context needed to later restore the component back to the F0 state.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> only transitions a component to or from the F0 state.

This function can be called simultaneously from multiple execution threads. However, only one thread at a time can call this function to control a particular  component.

The operating system guarantees that this function follows the zero level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level">Threading and Synchronization Zero Level</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentactive">DxgkCbSetPowerComponentActive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>

