---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTIDLE
title: DXGKCB_SETPOWERCOMPONENTIDLE (d3dkmddi.h)
description: Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed.
old-location: display\dxgkcbsetpowercomponentidle.htm
ms.assetid: 7746d09a-7fb6-4e5d-926c-4ded6830b06d
ms.date: 05/10/2018
ms.keywords: DXGKCB_SETPOWERCOMPONENTIDLE, DXGKCB_SETPOWERCOMPONENTIDLE callback, DxgkCbSetPowerComponentIdle, DxgkCbSetPowerComponentIdle callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentIdle, display.dxgkcbsetpowercomponentidle
ms.topic: callback
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
req.irql: See Remarks section.
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkCbSetPowerComponentIdle"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkCbSetPowerComponentIdle
product:
 - Windows
---

# DXGKCB_SETPOWERCOMPONENTIDLE callback function

## -description

Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed. After this function returns, the display miniport driver must not change the component's hardware settings.

## -parameters

### -param hAdapter

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param ComponentIndex

The power component index specified by  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

## -returns

This callback function does not return a value.

## -remarks

The display miniport driver can call this function for any type of power component, even if the DirectX graphics kernel subsystem manages the idle state of the component.

Each call to this function must be paired with a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentactive">DxgkCbSetPowerComponentActive</a> function.

When this function is called, the active reference count of the component is decreased by 1. The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

This function must be called at IRQL <= 		DISPATCH_LEVEL. It can be called at IRQL = 		DISPATCH_LEVEL only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentactive">DxgkCbSetPowerComponentActive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>

