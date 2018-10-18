---
UID: NC:d3dkmddi.DXGKCB_COMPLETEFSTATETRANSITION
title: DXGKCB_COMPLETEFSTATETRANSITION
author: windows-driver-content
description: Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to notify the port driver that a power component has completed the F-state transition.
old-location: display\dxgkcbcompletefstatetransition.htm
ms.assetid: 69a6d9bc-44a9-4204-988e-e11c80f67f28
ms.date: 5/10/2018
ms.keywords: DXGKCB_COMPLETEFSTATETRANSITION, DXGKCB_COMPLETEFSTATETRANSITION callback, DxgkCbCompleteFStateTransition, DxgkCbCompleteFStateTransition callback function [Display Devices], PDXGKCB_COMPLETEFSTATETRANSITION, d3dkmddi/DxgkCbCompleteFStateTransition, display.dxgkcbcompletefstatetransition
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
-	DxgkCbCompleteFStateTransition
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_COMPLETEFSTATETRANSITION callback function


## -description


Called by a Windows Display Driver Model (WDDM) 1.2 or later display miniport driver to notify the port driver that a power component has completed the F-state transition.


## -parameters




### -param hAdapter

[in] A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param ComponentIndex

The power component index specified by  <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.


## -returns



This callback function does not return a value.




## -remarks



During component registration the display miniport driver should indicate all power components for which it will need to call the <i>DxgkCbCompleteFStateTransition</i> function by setting the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464063">DXGK_POWER_COMPONENT_FLAGS</a>.<b>DriverCompletesFStateTransition</b> member to 1. When this member is set, the driver must call this function either synchronously or asynchronously. Conversely, if this member is not set, the driver should not call this function.

<div class="alert"><b>Note</b>  If the <a href="https://msdn.microsoft.com/library/windows/hardware/hh464063">DXGK_POWER_COMPONENT_FLAGS</a>.<b>DriverCompletesFStateTransition</b> member has been set but the driver does not call this function, deadlocks might occur.</div>
<div> </div>
The Windows power management framework guarantees that no new transition request will be sent for the component until this function is called.

Usually the port driver expects that when this function returns, the F-state transition is completed. There could be scenarios when the display miniport driver cannot complete the transition synchronously, for example if the display miniport driver cannot complete the transitions at <b>DISPATCH_LEVEL</b>, or it needs to activate other power components. This function helps the display miniport driver to complete the F-state transition asynchronously.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh464063">DXGK_POWER_COMPONENT_FLAGS</a>
 

 

