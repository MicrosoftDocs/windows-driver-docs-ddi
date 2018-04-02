---
UID: NC:d3dkmddi.DXGKDDISETPOWERCOMPONENTFSTATE
title: DXGKDDISETPOWERCOMPONENTFSTATE
author: windows-driver-content
description: Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state).
old-location: display\dxgkddisetpowercomponentfstate.htm
old-project: display
ms.assetid: C68CC6F1-83D6-43D9-93F3-99E3A990C7D7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDISETPOWERCOMPONENTFSTATE, DxgkDdiSetPowerComponentFState, DxgkDdiSetPowerComponentFState callback function [Display Devices], d3dkmddi/DxgkDdiSetPowerComponentFState, display.dxgkddisetpowercomponentfstate
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiSetPowerComponentFState
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---

# DXGKDDISETPOWERCOMPONENTFSTATE callback


## -description


Called by the Microsoft DirectX graphics kernel subsystem to transition a power component to an idle state (an F-state).


## -parameters




### -param DriverContext [in]

A handle to a context block associated with a display adapter. The display miniport driver's <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function previously provided this handle to the DirectX graphics kernel subsystem.


### -param ComponentIndex

The power component index specified by  <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.


### -param FState

An F-state value that the display miniport driver has reported to the DirectX graphics kernel subsystem.


## -returns




      Returns STATUS_SUCCESS if it succeeds; otherwise, it returns STATUS_INVALID_PARAMETER.




## -remarks



The operating system calls <i>DxgkDdiSetPowerComponentFState</i> only if the display miniport driver indicates support by setting <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>.<b>SupportRuntimePowerManagement</b> to <b>TRUE</b>.

<div class="alert"><b>Note</b>  To avoid a possible deadlock, do not call the <a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a> function until this function has returned.</div>
<div> </div>
When the display miniport driver transitions a power component from the F0 (fully on) state to another F-state, it should save the context needed to later restore the component back to the F0 state.

The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> only transitions a component to or from the F0 state.

This function can be called simultaneously from multiple execution threads. However, only one thread at a time can call this function to control a particular  component.

The operating system guarantees that this function follows the zero level synchronization mode as defined in <a href="https://msdn.microsoft.com/2baf91e8-fafb-40e2-a24c-cbf04fe45274">Threading and Synchronization Zero Level</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>
 

 

