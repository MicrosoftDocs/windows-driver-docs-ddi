---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTACTIVE
title: DXGKCB_SETPOWERCOMPONENTACTIVE (d3dkmddi.h)
description: Called by the display miniport driver to access a power component.
old-location: display\dxgkcbsetpowercomponentactive.htm
ms.assetid: 12008d80-8bcb-4289-97ea-d3325731a95f
ms.date: 05/10/2018
ms.keywords: DXGKCB_SETPOWERCOMPONENTACTIVE, DXGKCB_SETPOWERCOMPONENTACTIVE callback, DxgkCbSetPowerComponentActive, DxgkCbSetPowerComponentActive callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentActive, display.dxgkcbsetpowercomponentactive
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
 - "d3dkmddi/DxgkCbSetPowerComponentActive"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkCbSetPowerComponentActive
product:
 - Windows
---

# DXGKCB_SETPOWERCOMPONENTACTIVE callback function

## -description

Called by the display miniport driver to access a power component. After this function returns, the display miniport driver can change the component's hardware settings.

## -parameters

### -param hAdapter

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param ComponentIndex

The power component index specified by  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

## -remarks

Each call to this function must be paired with a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentidle">DxgkCbSetPowerComponentIdle</a> function to indicate that the component hardware is no longer required.

When this function is called, the active reference count of the component is increased by 1. The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

While calling this function, the display miniport driver might receive a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddisetpowercomponentfstate">DxgkDdiSetPowerComponentFState</a> function on another execution thread.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentidle">DxgkCbSetPowerComponentIdle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddisetpowercomponentfstate">DxgkDdiSetPowerComponentFState</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>

