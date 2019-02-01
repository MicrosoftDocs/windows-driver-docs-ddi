---
UID: NC:d3dkmddi.DXGKCB_SETPOWERCOMPONENTIDLE
title: DXGKCB_SETPOWERCOMPONENTIDLE (d3dkmddi.h)
description: Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed.
old-location: display\dxgkcbsetpowercomponentidle.htm
ms.assetid: 7746d09a-7fb6-4e5d-926c-4ded6830b06d
ms.date: 05/10/2018
ms.keywords: DXGKCB_SETPOWERCOMPONENTIDLE, DXGKCB_SETPOWERCOMPONENTIDLE callback, DxgkCbSetPowerComponentIdle, DxgkCbSetPowerComponentIdle callback function [Display Devices], d3dkmddi/DxgkCbSetPowerComponentIdle, display.dxgkcbsetpowercomponentidle
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkCbSetPowerComponentIdle
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_SETPOWERCOMPONENTIDLE callback function


## -description


Called by the display miniport driver to notify the Microsoft DirectX graphics kernel subsystem that a power component is no longer needed. After this function returns, the display miniport driver must not change the component's hardware settings.


## -parameters




### -param hAdapter [in]

A handle to the display adapter. The display miniport driver receives the handle from the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure in a call to its <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a> function.


### -param ComponentIndex

The power component index specified by  <a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>.<b>pInputData</b> in a call to the <a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a> function.


## -returns



This callback function does not return a value.




## -remarks



The display miniport driver can call this function for any type of power component, even if the DirectX graphics kernel subsystem manages the idle state of the component.

Each call to this function must be paired with a call to the <a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a> function.

When this function is called, the active reference count of the component is decreased by 1. The <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">Power Management Framework</a> maintains the reference count and places the component into a lower F-state only when the reference count becomes zero.

This function must be called at IRQL &lt;= 		DISPATCH_LEVEL. It can be called at IRQL = 		DISPATCH_LEVEL only if the component type is <b>DXGK_POWER_COMPONENT_OTHER</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557621">DXGKARG_QUERYADAPTERINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a>



<a href="https://msdn.microsoft.com/12008d80-8bcb-4289-97ea-d3325731a95f">DxgkCbSetPowerComponentActive</a>



<a href="https://msdn.microsoft.com/f2f4c54c-7413-48e5-a165-d71f35642b6c">DxgkDdiQueryAdapterInfo</a>



<a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>
 

 

