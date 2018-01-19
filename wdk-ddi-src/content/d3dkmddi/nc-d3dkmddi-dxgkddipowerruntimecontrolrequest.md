---
UID: NC:d3dkmddi.DXGKDDIPOWERRUNTIMECONTROLREQUEST
title: DXGKDDIPOWERRUNTIMECONTROLREQUEST
author: windows-driver-content
description: Called by the Power Engine Plug-in (PEP) to exchange information with the display miniport driver. Also called by the Microsoft DirectX graphics kernel subsystem to notify the display miniport driver about certain events.
old-location: display\dxgkddipowerruntimecontrolrequest.htm
old-project: display
ms.assetid: 56535128-3107-4fb5-b0e1-2e913c386cc2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiPowerRuntimeControlRequest
req.alt-loc: D3dkmddi.h
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
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDIPOWERRUNTIMECONTROLREQUEST callback



## -description
Called by the Power Engine Plug-in (PEP) to exchange information with the display miniport driver. Also called by the Microsoft DirectX graphics kernel subsystem to notify the display miniport driver about certain events.



## -prototype

````
PDXGKDDIPOWERRUNTIMECONTROLREQUEST DxgkDdiPowerRuntimeControlRequest;

_Check_return_ NTSTATUS APIENTRY* DxgkDdiPowerRuntimeControlRequest(
  _In_      const HANDLE  DriverContext,
  _In_            LPCGUID PowerControlCode,
  _In_opt_        PVOID   InBuffer,
  _In_            SIZE_T  InBufferSize,
  _Out_opt_       PVOID   OutBuffer,
  _In_            SIZE_T  OutBufferSize,
  _Out_opt_       PSIZE_T BytesReturned
)
{ ... }
````


## -parameters

### -param DriverContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param PowerControlCode [in]

A pointer to a GUID that defines the meaning of the PEP's control request. For more information, see Remarks.


### -param InBuffer [in, optional]

An optional pointer to an input buffer.


### -param InBufferSize [in]

The size, in bytes, of the buffer that <i>InBuffer</i> points to.


### -param OutBuffer [out, optional]

An optional pointer to an output buffer.


### -param OutBufferSize [in]

The size, in bytes, of the buffer that <i>OutBuffer</i> points to.


### -param BytesReturned [out, optional]

An optional pointer to a buffer that contains the number of bytes that are written by the display miniport driver to the output buffer.


## -returns
Returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.


## -remarks
The operating system calls <i>DxgkDdiPowerRuntimeControlRequest</i> only if the display miniport driver indicates support by setting <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>.<b>SupportRuntimePowerManagement</b> to <b>TRUE</b>.

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




Increase the voltage.

Decrease the voltage.

Change the voltage, but the driver doesn't know if the change is an increase or decrease.

Increase the clock setting.

Decrease the clock setting.

Change the clock setting, but the driver doesn't know if the change is an increase or decrease.

Increase the bandwidth.

Decrease the bandwidth.

Change the bandwidth, but the driver doesn't know if the change is an increase or decrease.

The DirectX graphics kernel subsystem uses the following GUIDs that are defined in D3dkmddi.h to notify the display miniport driver about certain events.

<dl>
<dt><a id="GUID_DXGKDDI_POWER_MANAGEMENT_PREPARE_TO_START"></a><a id="guid_dxgkddi_power_management_prepare_to_start"></a>GUID_DXGKDDI_POWER_MANAGEMENT_PREPARE_TO_START</dt>
<dd>
Used after the DirectX graphics kernel subsystem registers the device for runtime power management, but before the device is started. After this function has been called with this GUID, the display miniport driver can call these functions:

<ul>
<li>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a>
</li>
<li>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentlatency.md">DxgkCbSetPowerComponentLatency</a>
</li>
<li>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentresidency.md">DxgkCbSetPowerComponentResidency</a>
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


Used after the DirectX graphics kernel subsystem registers the device for runtime power management, but before the device is started. After this function has been called with this GUID, the display miniport driver can call these functions:

Used after the DirectX graphics kernel subsystem starts runtime power management. After this function has been called with this GUID, the display miniport driver can call any power runtime functions.

Used immediately before the DirectX graphics kernel subsystem unregisters the device for runtime power management. After this function has been called with this GUID, the display miniport driver should not call any power runtime functions.

This function can be called simultaneously from multiple execution threads.

The operating system guarantees that this function follows the zero level synchronization mode as defined in <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">Threading and Synchronization Zero Level</a>.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentlatency.md">DxgkCbSetPowerComponentLatency</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentresidency.md">DxgkCbSetPowerComponentResidency</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDXGKDDIPOWERRUNTIMECONTROLREQUEST callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

