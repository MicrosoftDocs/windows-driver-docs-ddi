---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTIDLE
title: DXGKCB_SETPOWERCOMPONENTIDLE (d3dkmddi.h)
description: Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed.
old-location: display\dxgkcbsetpowercomponentidle.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_SETPOWERCOMPONENTIDLE callback function"]
ms.keywords: DXGKCB_SETPOWERCOMPONENTIDLE, DXGKCB_SETPOWERCOMPONENTIDLE callback, DxgkCbSetPowerComponentIdle, DxgkCbSetPowerComponentIdle callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentIdle, display.dxgkcbsetpowercomponentidle
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8 (WDDM 1.2)
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
 - DXGKCB_SETPOWERCOMPONENTIDLE
 - d3dkmddi/DXGKCB_SETPOWERCOMPONENTIDLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_SETPOWERCOMPONENTIDLE
---

# DXGKCB_SETPOWERCOMPONENTIDLE callback function

## -description

A display miniport driver calls **DXGKCB_SETPOWERCOMPONENTIDLE** to notify the DirectX graphics kernel subsystem that a power component is no longer needed. After this function returns, the display miniport driver must not change the component's hardware settings.

## -parameters

### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param ComponentIndex [in]

The power component index specified by [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md).**pInputData** in a call to the [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

## -remarks

The display miniport driver can call this function for any type of power component, even if the DirectX graphics kernel subsystem manages the idle state of the component.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbSetPowerComponentIdle** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md). Each call to this function must be paired with a call to the [**DXGKCB_SETPOWERCOMPONENTACTIVE**](nc-d3dkmddi-dxgkcb_setpowercomponentactive.md) function.

When this function is called, the active reference count of the component is decreased by 1. The [Power Management Framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

This function must be called at IRQL <= DISPATCH_LEVEL. It can be called at IRQL = DISPATCH_LEVEL only if the component type is **DXGK_POWER_COMPONENT_OTHER**.

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)

[**DXGKCB_SETPOWERCOMPONENTACTIVE**](nc-d3dkmddi-dxgkcb_setpowercomponentactive.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
