---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTACTIVE
title: DXGKCB_SETPOWERCOMPONENTACTIVE (d3dkmddi.h)
description: Called by the display miniport driver to access a power component.
old-location: display\dxgkcbsetpowercomponentactive.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_SETPOWERCOMPONENTACTIVE callback function"]
ms.keywords: DXGKCB_SETPOWERCOMPONENTACTIVE, DXGKCB_SETPOWERCOMPONENTACTIVE callback, DxgkCbSetPowerComponentActive, DxgkCbSetPowerComponentActive callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentActive, display.dxgkcbsetpowercomponentactive
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_SETPOWERCOMPONENTACTIVE
 - d3dkmddi/DXGKCB_SETPOWERCOMPONENTACTIVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_SETPOWERCOMPONENTACTIVE
product:
 - Windows
---

# DXGKCB_SETPOWERCOMPONENTACTIVE callback function

## -description

A display miniport driver calls **DXGKCB_SETPOWERCOMPONENTACTIVE** to access a power component. After this function returns, the display miniport driver can change the component's hardware settings.

## -parameters

### -param hAdapter

[in] A handle to the display adapter. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param ComponentIndex

[in] The power component index specified by [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md).**pInputData** in a call to the [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

## -remarks

Each call to this function must be paired with a call to the [**DXGKCB_SETPOWERCOMPONENTIDLE**](nc-d3dkmddi-dxgkcb_setpowercomponentidle.md) function to indicate that the component hardware is no longer required.

When this function is called, the active reference count of the component is increased by 1. The [Power Management Framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

While calling this function, the display miniport driver might receive a call to the [**DxgkDdiSetPowerComponentFState**](nc-d3dkmddi-dxgkddisetpowercomponentfstate.md) function on another execution thread.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbSetPowerComponentActive** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)

[**DXGKCB_SETPOWERCOMPONENTIDLE**](nc-d3dkmddi-dxgkcb_setpowercomponentidle.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DxgkDdiSetPowerComponentFState**](nc-d3dkmddi-dxgkddisetpowercomponentfstate.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
