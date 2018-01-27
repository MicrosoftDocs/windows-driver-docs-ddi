---
UID: NC:d3dkmddi.DXGKDDISETPOWERCOMPONENTFSTATE
title: DXGKDDISETPOWERCOMPONENTFSTATE
author: windows-driver-content
description: Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state).
old-location: display\dxgkddisetpowercomponentfstate.htm
old-project: display
ms.assetid: C68CC6F1-83D6-43D9-93F3-99E3A990C7D7
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddisetpowercomponentfstate, DxgkDdiSetPowerComponentFState callback function [Display Devices], DxgkDdiSetPowerComponentFState, DXGKDDISETPOWERCOMPONENTFSTATE, DXGKDDISETPOWERCOMPONENTFSTATE, d3dkmddi/DxgkDdiSetPowerComponentFState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	D3dkmddi.h
apiname: 
-	DxgkDdiSetPowerComponentFState
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDISETPOWERCOMPONENTFSTATE callback


## -description


Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state).


## -prototype


````
DXGKDDISETPOWERCOMPONENTFSTATE DxgkDdiSetPowerComponentFState;

_Check_return_ NTSTATUS APIENTRY* DxgkDdiSetPowerComponentFState(
  _In_ const HANDLE DriverContext,
             UINT   ComponentIndex,
             UINT   FState
)
{ ... }
````


## -parameters




### -param DriverContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ComponentIndex

The power component index specified by  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


### -param FState

An F-state value that the display miniport driver has reported to the DirectX graphics kernel subsystem.


## -returns



      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns STATUS_INVALID_PARAMETER.



## -remarks


The operating system calls <i>DxgkDdiSetPowerComponentFState</i> only if the display miniport driver indicates support by setting <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>.<b>SupportRuntimePowerManagement</b> to <b>TRUE</b>.
<div class="alert"><b>Note</b>  To avoid a possible deadlock, do not call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a> function until this function has returned.</div><div> </div>When the display miniport driver transitions a power component from the F0 (fully on) state to another F-state, it should save the context needed to later restore the component back to the F0 state.

The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> only transitions a component to or from the F0 state.

This function can be called simultaneously from multiple execution threads. However, only one thread at a time can call this function to control a particular  component.

The operating system guarantees that this function follows the zero level synchronization mode as defined in <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">Threading and Synchronization Zero Level</a>.



## -see-also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>

<a href="..\dispmprt\ns-dispmprt-_dxgkrnl_interface.md">DXGKRNL_INTERFACE</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_setpowercomponentactive.md">DxgkCbSetPowerComponentActive</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDISETPOWERCOMPONENTFSTATE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

