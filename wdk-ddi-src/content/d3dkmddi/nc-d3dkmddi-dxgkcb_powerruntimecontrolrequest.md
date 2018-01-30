---
UID: NC:d3dkmddi.DXGKCB_POWERRUNTIMECONTROLREQUEST
title: DXGKCB_POWERRUNTIMECONTROLREQUEST
author: windows-driver-content
description: Called by the display miniport driver to exchange information with the Power Engine Plug-in (PEP).
old-location: display\dxgkcbpowerruntimecontrolrequest.htm
old-project: display
ms.assetid: 28984c89-a1d9-4720-8c4c-2b2ce34e0899
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbpowerruntimecontrolrequest, PDXGKCB_POWERRUNTIMECONTROLREQUEST, DxgkCbPowerRuntimeControlRequest callback function [Display Devices], DxgkCbPowerRuntimeControlRequest, DXGKCB_POWERRUNTIMECONTROLREQUEST, DXGKCB_POWERRUNTIMECONTROLREQUEST, d3dkmddi/DxgkCbPowerRuntimeControlRequest
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3dkmddi.h
apiname:
-	DxgkCbPowerRuntimeControlRequest
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_POWERRUNTIMECONTROLREQUEST callback


## -description


Called by the display miniport driver to exchange information with the Power Engine Plug-in (PEP).


## -prototype


````
DXGKCB_POWERRUNTIMECONTROLREQUEST DxgkCbPowerRuntimeControlRequest;

NTSTATUS APIENTRY CALLBACK* DxgkCbPowerRuntimeControlRequest(
  _In_      const HANDLE  hAdapter,
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




### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure in a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param LPCGUID



### -param OPTIONAL






### -param SIZE_T



#### - PowerControlCode [in]

A pointer to a GUID that defines the meaning of the display miniport driver's control request. For more information, see Remarks.


#### - InBuffer [in, optional]

An optional pointer to an input buffer.


#### - InBufferSize [in]

The size, in bytes, of the buffer that <i>InBuffer</i> points to.


#### - OutBuffer [out, optional]

An optional pointer to an output buffer.


#### - OutBufferSize [in]

The size, in bytes, of the buffer that <i>OutBuffer</i> points to.


#### - BytesReturned [out, optional]

An optional pointer to a buffer that contains the number of bytes that are written by the PEP to the output buffer.


## -returns


Returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in Ntstatus.h.



## -remarks


<div class="alert"><b>Note</b>  To avoid a possible deadlock, do not call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a> function until this function has returned.</div><div> </div>Although the driver can use any GUID in the <i>PowerControlCode</i> parameter, the following GUIDs that are defined in D3dkmddi.h are recommended. By using these GUIDs, the display port driver can issue Event Tracing for Windows (ETW) events, which are useful to profile driver performance issues.

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

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a>

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>

<a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_POWERRUNTIMECONTROLREQUEST callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

