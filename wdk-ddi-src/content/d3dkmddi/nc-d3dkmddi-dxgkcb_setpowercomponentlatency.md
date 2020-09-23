---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTLATENCY
title: DXGKCB_SETPOWERCOMPONENTLATENCY (d3dkmddi.h)
description: Called by the display miniport driver to set the latency tolerance for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentlatency.htm
ms.assetid: 8FF86746-15A2-4BDF-98AF-23B5F9960DB9
ms.date: 05/10/2018
keywords: ["DXGKCB_SETPOWERCOMPONENTLATENCY callback function"]
ms.keywords: DXGKCB_SETPOWERCOMPONENTLATENCY, DXGKCB_SETPOWERCOMPONENTLATENCY callback, DxgkCbSetPowerComponentLatency, DxgkCbSetPowerComponentLatency callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentLatency, display.dxgkcbsetpowercomponentlatency
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
 - DxgkCbSetPowerComponentLatency
product:
 - Windows
---

# DXGKCB_SETPOWERCOMPONENTLATENCY callback function


## -description

Called by the display miniport driver to set the latency tolerance for a power component of type <b>DXGK_POWER_COMPONENT_OTHER</b>.

## -parameters

### -param hAdapter

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure in a call to its <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.

### -param ComponentIndex

The power component index specified by  <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.

### -param Latency

The <i>latency tolerance</i>—the maximum  time, in units of 100 nanoseconds, that the display miniport driver should take to awaken a power component from an idle state. The <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> uses this information to select an appropriate idle state for the component that does not violate the requested latency tolerance. The latency tolerance specified by <i>Latency</i> remains in effect until the driver calls this function again to update it.

For more information, see Remarks.

## -remarks

<div class="alert"><b>Note</b>  The display miniport driver should call this function only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>. The Microsoft DirectX graphics kernel subsystem sets the latency tolerance value for other component types.</div>
<div> </div>
If the power component is in an idle state when this function is called, the <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Power Management Framework</a> might change the component's F-state to meet the latency tolerance specified by <i>Latency</i>.

If the driver sets <i>Latency</i> to a value of <b>PO_FX_UNKNOWN_TIME</b> (defined in Wdm.h), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a>