---
UID: NC:d3dkmddi.DXGKDDIPOWERRUNTIMECONTROLREQUEST
title: DXGKDDIPOWERRUNTIMECONTROLREQUEST (d3dkmddi.h)
description: Called by the Power Engine Plug-in (PEP) to exchange information with the display miniport driver. Also called by the Microsoft DirectX graphics kernel subsystem to notify the display miniport driver about certain events.
old-location: display\dxgkddipowerruntimecontrolrequest.htm
ms.assetid: 56535128-3107-4fb5-b0e1-2e913c386cc2
ms.date: 05/10/2018
ms.keywords: DxgkDdiPowerRuntimeControlRequest, DxgkDdiPowerRuntimeControlRequest callback function [Display Devices], PDXGKDDIPOWERRUNTIMECONTROLREQUEST, PDXGKDDIPOWERRUNTIMECONTROLREQUEST callback, d3dkmddi/DxgkDdiPowerRuntimeControlRequest, display.dxgkddipowerruntimecontrolrequest
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
 - "d3dkmddi/DxgkDdiPowerRuntimeControlRequest"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3dkmddi.h
api_name:
 - DxgkDdiPowerRuntimeControlRequest
product:
 - Windows
---

# DXGKDDIPOWERRUNTIMECONTROLREQUEST callback function

## -description

Called by the Power Engine Plug-in (PEP) to exchange information with the display miniport driver. Also called by the Microsoft DirectX graphics kernel subsystem to notify the display miniport driver about certain events.

## -parameters

### -param DriverContext

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.

### -param PowerControlCode

A pointer to a GUID that defines the meaning of the PEP's control request. For more information, see Remarks.

### -param InBuffer

An optional pointer to an input buffer.

### -param InBufferSize

The size, in bytes, of the buffer that <i>InBuffer</i> points to.

### -param OutBuffer

An optional pointer to an output buffer.

### -param OutBufferSize

The size, in bytes, of the buffer that <i>OutBuffer</i> points to.

### -param BytesReturned

An optional pointer to a buffer that contains the number of bytes that are written by the display miniport driver to the output buffer.

## -returns

Returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.

## -remarks

The operating system calls <i>DxgkDdiPowerRuntimeControlRequest</i> only if the display miniport driver indicates support by setting <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>.<b>SupportRuntimePowerManagement</b> to <b>TRUE</b>.

<h3><a id="GUIDs_used_by_the_Power_Engine_Plugin__PEP_"></a><a id="guids_used_by_the_power_engine_plugin__pep_"></a><a id="GUIDS_USED_BY_THE_POWER_ENGINE_PLUGIN__PEP_"></a>GUIDs used by the Power Engine Plugin (PEP)</h3>
The PEP uses the following GUIDs that are defined in D3dkmddi.h to exchange information with the display miniport driver. The display port driver uses these  GUIDs to issue Event Tracing for Windows (ETW) events, which are useful to profile driver performance issues.

<dl>
<dt><a id="GUID_DXGKDDI_POWER_VOLTAGE_UP"></a><a id="guid_dxgkddi_power_voltage_up"></a>GUID_DXGKDDI_POWER_VOLTAGE_UP</dt>
<dd>
Increase the voltage.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_VOLTAGE_DOWN"></a><a id="guid_dxgkddi_power_voltage_down"></a>GUID_DXGKDDI_POWER_VOLTAGE_DOWN</dt>
<dd>
Decrease the voltage.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_VOLTAGE"></a><a id="guid_dxgkddi_power_voltage"></a>GUID_DXGKDDI_POWER_VOLTAGE</dt>
<dd>
Change the voltage, but the driver doesn't know if the change is an increase or decrease.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_CLOCK_UP"></a><a id="guid_dxgkddi_power_clock_up"></a>GUID_DXGKDDI_POWER_CLOCK_UP</dt>
<dd>
Increase the clock setting.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_CLOCK_DOWN"></a><a id="guid_dxgkddi_power_clock_down"></a>GUID_DXGKDDI_POWER_CLOCK_DOWN</dt>
<dd>
Decrease the clock setting.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_CLOCK"></a><a id="guid_dxgkddi_power_clock"></a>GUID_DXGKDDI_POWER_CLOCK</dt>
<dd>
Change the clock setting, but the driver doesn't know if the change is an increase or decrease.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_BANDWIDTH_UP"></a><a id="guid_dxgkddi_power_bandwidth_up"></a>GUID_DXGKDDI_POWER_BANDWIDTH_UP</dt>
<dd>
Increase the bandwidth.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_BANDWIDTH_DOWN"></a><a id="guid_dxgkddi_power_bandwidth_down"></a>GUID_DXGKDDI_POWER_BANDWIDTH_DOWN</dt>
<dd>
Decrease the bandwidth.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_BANDWIDTH"></a><a id="guid_dxgkddi_power_bandwidth"></a>GUID_DXGKDDI_POWER_BANDWIDTH</dt>
<dd>
Change the bandwidth, but the driver doesn't know if the change is an increase or decrease.

</dd>
</dl>


<h3><a id="GUIDs_used_by_the_DirectX_graphics_kernel_subsystem"></a><a id="guids_used_by_the_directx_graphics_kernel_subsystem"></a><a id="GUIDS_USED_BY_THE_DIRECTX_GRAPHICS_KERNEL_SUBSYSTEM"></a>GUIDs used by the DirectX graphics kernel subsystem</h3>
The DirectX graphics kernel subsystem uses the following GUIDs that are defined in D3dkmddi.h to notify the display miniport driver about certain events.

<dl>
<dt><a id="GUID_DXGKDDI_POWER_MANAGEMENT_PREPARE_TO_START"></a><a id="guid_dxgkddi_power_management_prepare_to_start"></a>GUID_DXGKDDI_POWER_MANAGEMENT_PREPARE_TO_START</dt>
<dd>
Used after the DirectX graphics kernel subsystem registers the device for runtime power management, but before the device is started. After this function has been called with this GUID, the display miniport driver can call these functions:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentactive">DxgkCbSetPowerComponentActive</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentlatency">DxgkCbSetPowerComponentLatency</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentresidency">DxgkCbSetPowerComponentResidency</a>
</li>
</ul>
</dd>
<dt><a id="GUID_DXGKDDI_POWER_MANAGEMENT_STARTED"></a><a id="guid_dxgkddi_power_management_started"></a>GUID_DXGKDDI_POWER_MANAGEMENT_STARTED</dt>
<dd>
Used after the DirectX graphics kernel subsystem starts runtime power management. After this function has been called with this GUID, the display miniport driver can call any power runtime functions.

</dd>
<dt><a id="GUID_DXGKDDI_POWER_MANAGEMENT_STOPPED"></a><a id="guid_dxgkddi_power_management_stopped"></a>GUID_DXGKDDI_POWER_MANAGEMENT_STOPPED</dt>
<dd>
Used immediately before the DirectX graphics kernel subsystem unregisters the device for runtime power management. After this function has been called with this GUID, the display miniport driver should not call any power runtime functions.

</dd>
</dl>


<h3><a id="Synchronization"></a><a id="synchronization"></a><a id="SYNCHRONIZATION"></a>Synchronization</h3>
This function can be called simultaneously from multiple execution threads.

The operating system guarantees that this function follows the zero level synchronization mode as defined in <a href="https://docs.microsoft.com/windows-hardware/drivers/display/threading-and-synchronization-zero-level">Threading and Synchronization Zero Level</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_queryadapterinfo">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_drivercaps">DXGK_DRIVERCAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentactive">DxgkCbSetPowerComponentActive</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentlatency">DxgkCbSetPowerComponentLatency</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_setpowercomponentresidency">DxgkCbSetPowerComponentResidency</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a>

