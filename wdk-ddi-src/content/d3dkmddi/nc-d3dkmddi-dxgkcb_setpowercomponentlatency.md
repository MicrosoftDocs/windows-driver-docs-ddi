---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTLATENCY
title: DXGKCB_SETPOWERCOMPONENTLATENCY
author: windows-driver-content
description: Called by the display miniport driver to set the latency tolerance for a power component of type DXGK_POWER_COMPONENT_OTHER.
old-location: display\dxgkcbsetpowercomponentlatency.htm
old-project: display
ms.assetid: 8FF86746-15A2-4BDF-98AF-23B5F9960DB9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkcbsetpowercomponentlatency, DxgkCbSetPowerComponentLatency callback function [Display Devices], DxgkCbSetPowerComponentLatency, DXGKCB_SETPOWERCOMPONENTLATENCY, DXGKCB_SETPOWERCOMPONENTLATENCY, d3dkmddi/DxgkCbSetPowerComponentLatency
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
-	DxgkCbSetPowerComponentLatency
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKCB_SETPOWERCOMPONENTLATENCY callback


## -description


Called by the display miniport driver to set the latency tolerance for a power component of type <b>DXGK_POWER_COMPONENT_OTHER</b>.


## -prototype


````
DXGKCB_SETPOWERCOMPONENTLATENCY DxgkCbSetPowerComponentLatency;

VOID APIENTRY CALLBACK* DxgkCbSetPowerComponentLatency(
  _In_ const HANDLE    hAdapter,
             UINT      ComponentIndex,
             ULONGLONG Latency
)
{ ... }
````


## -parameters




### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a> structure in a call to its <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -param ComponentIndex

The power component index specified by  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


### -param Latency

The <i>latency tolerance</i>—the maximum  time, in units of 100 nanoseconds, that the display miniport driver should take to awaken a power component from an idle state. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> uses this information to select an appropriate idle state for the component that does not violate the requested latency tolerance. The latency tolerance specified by <i>Latency</i> remains in effect until the driver calls this function again to update it.

For more information, see Remarks.


## -returns


This callback function does not return a value.



## -remarks


<div class="alert"><b>Note</b>  The display miniport driver should call this function only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>. The Microsoft DirectX graphics kernel subsystem sets the latency tolerance value for other component types.</div><div> </div>If the power component is in an idle state when this function is called, the <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> might change the component's F-state to meet the latency tolerance specified by <i>Latency</i>.

If the driver sets <i>Latency</i> to a value of <b>PO_FX_UNKNOWN_TIME</b> (defined in Wdm.h), the Power Engine Plug-in (PEP) might be unable to set the component to an F-state lower than F0.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>

<a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_SETPOWERCOMPONENTLATENCY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

