---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTLATENCY
title: DXGKCB_SETPOWERCOMPONENTLATENCY (d3dkmddi.h)
description: Called by the display miniport driver to set the latency tolerance for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentlatency.htm
ms.date: 10/13/2021
keywords: ["DXGKCB_SETPOWERCOMPONENTLATENCY callback function"]
ms.keywords: DXGKCB_SETPOWERCOMPONENTLATENCY, DXGKCB_SETPOWERCOMPONENTLATENCY callback, DxgkCbSetPowerComponentLatency, DxgkCbSetPowerComponentLatency callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentLatency, display.dxgkcbsetpowercomponentlatency
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
 - DXGKCB_SETPOWERCOMPONENTLATENCY
 - d3dkmddi/DXGKCB_SETPOWERCOMPONENTLATENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DXGKCB_SETPOWERCOMPONENTLATENCY
---

# DXGKCB_SETPOWERCOMPONENTLATENCY callback function

## -description

A display miniport driver calls **DXGKCB_SETPOWERCOMPONENTLATENCY** to set the latency tolerance for a power component of type **DXGK_POWER_COMPONENT_OTHER**.

## -parameters

### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the **DeviceHandle** member of the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md) structure in a call to its [**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md) function.

### -param ComponentIndex [in]

The power component index specified by [**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md).**pInputData** in a call to the [**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

### -param Latency [in]

The *latency tolerance* — the maximum time, in units of 100 nanoseconds — that the display miniport driver should take to awaken a power component from an idle state. The [Power Management Framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) uses this information to select an appropriate idle state for the component that does not violate the requested latency tolerance. The latency tolerance specified by **Latency** remains in effect until the driver calls this function again to update it. See Remarks.

## -remarks

> [!NOTE]
>
> The display miniport driver should call this function only if the component type is **DXGK_POWER_COMPONENT_OTHER**. The DirectX graphics kernel subsystem sets the latency tolerance value for other component types.

*DXGKCB_XXX* functions are implemented by *Dxgkrnl*. To use this callback function, call **DxgkCbSetPowerComponentLatency** via the [**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md).

If the power component is in an idle state when this function is called, the [Power Management Framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) might change the component's F-state to meet the latency tolerance specified by **Latency**.

If the driver sets **Latency** to a value of **PO_FX_UNKNOWN_TIME** (defined in *Wdm.h*), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.

## -see-also

[**DXGKARG_QUERYADAPTERINFO**](ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)

[**DXGKRNL_INTERFACE**](../dispmprt/ns-dispmprt-_dxgkrnl_interface.md)

[**DxgkDdiQueryAdapterInfo**](nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DxgkDdiStartDevice**](../dispmprt/nc-dispmprt-dxgkddi_start_device.md)
