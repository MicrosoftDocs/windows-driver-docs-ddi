---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTRESIDENCY
title: DXGKCB_SETPOWERCOMPONENTRESIDENCY (d3dkmddi.h)
description: Called by the display miniport driver to set the expected residency for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentresidency.htm
ms.assetid: 9D567380-2E77-4A63-8674-E19A13C7B8BC
ms.date: 05/10/2018
ms.keywords: DXGKCB_SETPOWERCOMPONENTRESIDENCY, DXGKCB_SETPOWERCOMPONENTRESIDENCY callback, DxgkCbSetPowerComponentResidency, DxgkCbSetPowerComponentResidency callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentResidency, display.dxgkcbsetpowercomponentresidency
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3dkmddi/DxgkCbSetPowerComponentResidency"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkCbSetPowerComponentResidency
product:
 - Windows
---

# DXGKCB_SETPOWERCOMPONENTRESIDENCY callback function

## -description

Called by the display miniport driver to set the expected residency for a power component of type <b>DXGK_POWER_COMPONENT_OTHER</b>.

## -parameters

### -param hAdapter

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param ComponentIndex

The power component index specified by  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

### -param Residency

The <i>expected residency</i>—the maximum  time, in units of 100 nanoseconds, that the display miniport driver expects a power component to remain idle after it enters an idle state. The <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> uses this information to select an appropriate idle state for the component that does not violate the requested residency. The expected residency specified by <i>Residency</i> remains in effect until the driver calls this function again to update it.

For more information, see Remarks.

## -returns

This callback function does not return a value.

## -remarks

<div class="alert"><b>Note</b>  The display miniport driver should call this function only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>. The Microsoft DirectX graphics kernel subsystem sets the expected residency value for other component types.</div>
<div> </div>
If the power component is in an idle state when this function is called, the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> might change the component's F-state to meet the expected residency value specified by <i>Residency</i>.

If the driver sets <i>Residency</i> to a value of <b>PO_FX_UNKNOWN_TIME</b> (defined in Wdm.h), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>

