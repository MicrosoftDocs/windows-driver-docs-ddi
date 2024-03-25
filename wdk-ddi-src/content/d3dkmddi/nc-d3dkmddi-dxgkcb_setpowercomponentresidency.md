---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTRESIDENCY
title: DXGKCB_SETPOWERCOMPONENTRESIDENCY (d3dkmddi.h)
description: Called by the display miniport driver to set the expected residency for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentresidency.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_SETPOWERCOMPONENTRESIDENCY callback function"]
ms.keywords: DXGKCB_SETPOWERCOMPONENTRESIDENCY, DXGKCB_SETPOWERCOMPONENTRESIDENCY callback, DxgkCbSetPowerComponentResidency, DxgkCbSetPowerComponentResidency callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentResidency, display.dxgkcbsetpowercomponentresidency
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKCB_SETPOWERCOMPONENTRESIDENCY
 - d3dkmddi/DXGKCB_SETPOWERCOMPONENTRESIDENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_SETPOWERCOMPONENTRESIDENCY
---

# DXGKCB_SETPOWERCOMPONENTRESIDENCY callback function

## -description

A kernel-mode display miniport driver calls **DXGKCB_SETPOWERCOMPONENTRESIDENCY** to set the expected residency for a power component of type **DXGK_POWER_COMPONENT_OTHER**.

## -parameters

### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param ComponentIndex [in]

The power component index specified by [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md).**pInputData** in a call to the [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

### -param Residency [in]

The expected residency — the maximum time, in units of 100 nanoseconds — that the display miniport driver expects a power component to remain idle after it enters an idle state. The [Power Management Framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) uses this information to select an appropriate idle state for the component that does not violate the requested residency. The expected residency specified by **Residency** remains in effect until the driver calls this function again to update it. See Remarks.

## -remarks

> [!NOTE]
>
> The display miniport driver should call this function only if the component type is **DXGK_POWER_COMPONENT_OTHER**. The DirectX graphics kernel subsystem sets the expected residency value for other component types.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbSetPowerComponentResidency** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

If the power component is in an idle state when this function is called, the [Power Management Framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) might change the component's F-state to meet the expected residency value specified by **Residency**.

If the driver sets **Residency** to a value of **PO_FX_UNKNOWN_TIME** (defined in *Wdm.h*), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
