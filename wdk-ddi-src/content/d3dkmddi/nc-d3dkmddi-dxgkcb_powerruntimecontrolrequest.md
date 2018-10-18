---
UID: NC:d3dkmddi.DXGKCB_POWERRUNTIMECONTROLREQUEST
title: DXGKCB_POWERRUNTIMECONTROLREQUEST
author: windows-driver-content
description: Called by the display miniport driver to exchange information with the Power Engine Plug-in (PEP).
old-location: display\dxgkcbpowerruntimecontrolrequest.htm
ms.assetid: 28984c89-a1d9-4720-8c4c-2b2ce34e0899
ms.date: 05/10/2018
ms.keywords: DXGKCB_POWERRUNTIMECONTROLREQUEST, DXGKCB_POWERRUNTIMECONTROLREQUEST callback, DxgkCbPowerRuntimeControlRequest, DxgkCbPowerRuntimeControlRequest callback function [Display Devices], PDXGKCB_POWERRUNTIMECONTROLREQUEST, d3dkmddi/DxgkCbPowerRuntimeControlRequest, display.dxgkcbpowerruntimecontrolrequest
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkCbPowerRuntimeControlRequest
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_POWERRUNTIMECONTROLREQUEST callback function


## -description


Called by the display miniport driver to exchange information with the Power Engine Plug-in (PEP).


## -parameters




### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param LPCGUID

*PowerControlCode* [in]

A pointer to a GUID that defines the meaning of the display miniport driver's control request. For more information, see Remarks.

### -param OPTIONAL

*InBuffer* [in, optional]

An optional pointer to an input buffer.


### -param SIZE_T

*InBufferSize* [in]

The size, in bytes, of the buffer that <i>InBuffer (OPTIONAL)</i> points to.

### -param OPTIONAL

*OutBuffer* [out, optional]

An optional pointer to an output buffer.

### -param SIZE_T

*OutBufferSize* [in]

The size, in bytes, of the buffer that <i>OutBuffer</i> points to.

### -param OPTIONAL

*BytesReturned* [out, optional]

An optional pointer to a buffer that contains the number of bytes that are written by the PEP to the output buffer.



## -returns



Returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.




## -remarks



<div class="alert"><b>Note</b>  To avoid a possible deadlock, do not call the <a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a> function until this function has returned.</div>
<div> </div>
Although the driver can use any GUID in the <i>PowerControlCode</i> parameter, the following GUIDs that are defined in D3dkmddi.h are recommended. By using these GUIDs, the display port driver can issue Event Tracing for Windows (ETW) events, which are useful to profile driver performance issues.

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


These GUIDs do not imply that there is any communication protocol between the display miniport driver and the PEP, nor do they imply that there are any restrictions on the values that can be passed between the display miniport driver and the PEP.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

